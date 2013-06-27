---
layout: post
title:  "Kendo UI View Loader"
date:   2013-06-26 13:03:31
categories: javascript kendoui
---

{% highlight javascript %}
; (function ($, kendo) {
    this.kendoViewLoader = function (templatesUrl) {
        var templates = {};
        return function (templateName, viewModel, callback) {
            var template;
            function initView(templ) {
                callback(new kendo.View(templ, viewModel));
            }
            if (template = templates[templateName]) {
                initView(template);
            } else {
                if (template = $('#' + templateName).html()) {
                    initView(templates[templateName] = template);
                } else {
                    $.get(templatesUrl + '/' + 
                        encodeURIComponent(templateName), function (data) {
                            initView(templates[templateName] = data);
                        });
                }
            }
        };
    };
})($, kendo);

$(function() {
    var layout = new kendo.Layout("layout-tmpl");
    var viewLoader = kendoViewLoader('http://www.test.com/template/load');
    var app = new kendo.Router({
        init: function() {
            layout.render("#container");
        }
    });
    app.route('/', function() {
        viewLoader('product-list', {}, function(view) {
            layout.showIn('#content', view);
        });
    });
    app.route('/details', function() {
        viewLoader('product-details', {}, function(view) {
            layout.showIn('#content', view);
        });
    });
    app.start();
});
{% endhighlight %}

