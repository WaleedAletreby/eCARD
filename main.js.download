

//Making the modal overlay static, making buttons underneath not clickable
// 10-20-2017
$.fn.modal.prototype.constructor.Constructor.DEFAULTS.backdrop = 'static';

// Calling Accessible Menu
/*global jQuery */
if (jQuery) {
    (function ($) {
        "use strict";
        $(document).ready(function () {
            // initialize the megamenu
            //$('.dropdown').accessibleMegaMenu();

            $("div.megamenu").accessibleMegaMenu().addClass('moveIntoView');


            // hack so that the megamenu doesn't show flash of css animation after the page loads.
            //setTimeout(function () {
                //$('body').removeClass('init');

            //}, 500);
        });
    }(jQuery));
}

// - - - - - - - - - - - - - - - - - - - - - - - - - - -

jQuery( document ).ready(function( $ ) {

		var flyoutmenutrigger = window.document.querySelector('.accessible-megamenu-top-nav-item a');
		var isTouch = typeof window.hasOwnProperty === "function" && !!window.hasOwnProperty("ontouchstart");
	
		if(flyoutmenutrigger && isTouch) {
			flyoutmenutrigger.addEventListener('click', function(event) {   
				if(isTouch) {
					var flyoutmenu = window.document.querySelector('.accessible-megamenu-panel')
					if(flyoutmenu.classList.contains('open')) {
						flyoutmenu.classList.remove('open');
					} else {
						flyoutmenu.classList.add('open');
					};

					if(flyoutmenutrigger.classList.contains('open')) {
						flyoutmenutrigger.classList.remove('open');
					} else {
						flyoutmenutrigger.classList.add('open');
					};
				}

			})
		}

    if($.fn.smoothScroll){
        //Smooth Scroll Js
        // $('a').smoothScroll();
    }

    $('.fullHeight').setFullHeight();

    $(window).resize(function(){
        $('.fullHeight').setFullHeight();
    });

    //Chosen select
    // Turing off Chosen select because of screen reader
    //jQuery("select.chosen-select").chosen({width:'100%',disable_search: false});

    /*if($.fn.chosen){
        if($('.chosen-select').length){
            jQuery('.chosen-select').on('change', function (evt, params) {
                var selectedValue = params.selected;
                var arr = [];
                console.log(this.value);
                arr.push(selectedValue);
                arr.push( $( ".chosen-select option:selected" ).text());
                $('#chosen-output').text(arr.join(", "));
                console.log($( ".chosen-select option:selected" ).text());//output the text value
            });
        }
    }*/

  

    //Datepicker call
    /*if($.fn.datepicker){
        if($('.datepicker').length){
            $('.datepicker').datepicker({
                autoclose: true
                //,endDate: '-1d'
            });
        }
    }*/

    //Radio button value
    // Going to to standard browser form components because of screen reader and accessibility
    /*$('.radio').on('toggle',function(e) {
        var $el = $(e.target);
        var elname = e.target.name;
        //console.log($el.val());
        //console.log(elname);
    });*/

    //Checkbox button value
    // Going to to standard browser form components because of screen reader and accessibility
    /*$('.checkbox').on('toggle',function(e) {
        var $el = $(e.target);
        var elname = e.target.name;
        //console.log($el.val());
        //console.log(elname);
        //console.log($el.prop("checked"));
    });
    */

    //Muliple Select call
    if ($.fn.multipleSelect){
        if ($('select.select-multiple').length){
            $('select.select-multiple').multipleSelect();
        }
    }


    //Tooltips - Popover
    $('[data-toggle="popover"]').popover();

    //Sticky Admin Bar
    $(".makeSticky").sticky({topSpacing:0,zIndex:9999});


});

//MOBILE MENU
$(document).ready(function(){
    $('#mobileMenuClose').find('a').on('click',function (e) {
        e.preventDefault();
        var mainContent = $('#mainContentWrapper');
        if (mainContent.hasClass('openMenu')){
            mainContent.removeClass('openMenu').addClass('closeMenu');
        }else{
            mainContent.addClass('closeMenu');
        }
        mainContent.toggleClass('noScroll');
    });

    //Open Mobile Menu
    $('#openMobileMenu').on('click',function(e){
        e.preventDefault();
        var mainContent = $('#mainContentWrapper');

        if (mainContent.hasClass('closeMenu')){
            mainContent.removeClass('closeMenu').addClass('openMenu');
        }else{
            mainContent.addClass('openMenu');
        }
        mainContent.addClass('noScroll');
    });
});
