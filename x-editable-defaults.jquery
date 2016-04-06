(function ($) {

    var old_create_input = $.fn.editableutils.createInput;
    var inputs = ["text","textarea","select","date","datetime","dateui","combodate","html5types","checklist","wysihtml5","typeahead", "typeaheadjs", "select2"];


    for (var i=0; i < inputs.length; i++) {
        if ($.fn.editable.defaults[inputs[i]] == undefined) {
            $.fn.editable.defaults[inputs[i]] = {
                filters: [],
                addFilter: function(callback) {
                    this.filters.push(callback);
                }
            };
        }
    }

    $.fn.editableutils.createInput = function(options) {
        var defaults = $.fn.editable.defaults[options.type];

        if (defaults != undefined) {


            for (var i=0; i<defaults.filters.length; i++) {
                var _options = defaults.filters[i](options);
                if (_options != undefined) {
                    options = _options;
                }
            }

            $.extend(options, defaults);
        }

        return old_create_input.call(this, options);
    };
})(jQuery);
