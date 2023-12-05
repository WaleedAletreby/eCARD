/* -------------------------------------------------------------------------- */
/*                             CPR UI Interactions                            */
/* -------------------------------------------------------------------------- */

var CPRActions = CPRActions || {};

CPRActions.Dropdowns = (function(w,d){
    
    //Private
    function toggleDropdown() {

        var ddtoggles = document.querySelectorAll('header .dropdown-toggle');

        Array.prototype.slice.call(ddtoggles).forEach(function(ddtoggle) {
            var _ddtoggle = ddtoggle;
            
            var parent = _ddtoggle.parentElement;
            var ddmenu = _ddtoggle.nextElementSibling;
            var arrow = ddmenu.querySelector('.c-nav-dropdown__arrow');
            
            //var isShown = !ddmenu.dataset['state']; //string
            
            //let _code = evt.target.dataset["tierCode"];
            console.log("data-state: = ", ddmenu.dataset['state']);
            //console.log("this: ", this);
            // Position & Width with button
            var offsetleft, offsetwidth;
            offsetleft = _ddtoggle.offsetLeft;
            offsetwidth = _ddtoggle.offsetWidth;
            
            if(arrow !== 'undefined' || arrow !== null) {
                arrow.style.left = String(offsetleft + (offsetwidth / 2) - (20) + 'px');
            }


            /* -------------------------------------------------------------------------- */
            _ddtoggle.addEventListener('click', function(event) {
                console.log("clicked");
                //isShown = !isShown;
                var isShown = (ddmenu.dataset['state'] === "false") ? false : true ;
                console.log("isShown clicked: ", isShown);
                console.log("typeof isShown: ", typeof isShown);
        
                setIsShown(!isShown);
                ddmenu.dataset['state'] = String(!isShown);
            }, true);

            /* -------------------------------------------------------------------------- */
            function setIsShown(state) {
                var _state = state;
                toggleClass(parent, 'show', _state);
                toggleClass(ddmenu, 'is-shown', _state);
                toggleClass(ddmenu, 'is-visible', _state);
                toggleAria(_ddtoggle, _state);
                
        
            }
            /* -------------------------------------------------------------------------- */
            function clickOutside(event) {
                var isOutside = (event.target === _ddtoggle || event.target === _ddtoggle.querySelector('span')  || event.target === ddmenu || event.target === ddmenu.querySelector('ul')) ? false : true;
                if (isOutside == true) {
                    setIsShown(false);
                    ddmenu.dataset['state'] = String(false);
                }

            }
            
            document.addEventListener('click', clickOutside, true);
            /* -------------------------------------------------------------------------- */

        });

    }

    

    function toggleAria(el, state) {
        var _el = el;
        
        if(!state) {
            _el.ariaExpanded = "false";
        } else {
            _el.ariaExpanded = "true";
        }
    }

    function toggleClass(el, className, state) {
        var _el = el, _clasName = className, _state = state;

        if(!_state) {
            //false
            if(_el.classList.contains(_clasName)) {
                _el.classList.remove(_clasName);
            }
        } else {
            //true
            _el.classList.add(_clasName);
        }

    }

    function toggleStyle(el, style, state) {
        if(state === false) {
            el.style.cssText = style; 
        } else {
            el.style = ''
        }
    }

    function toggleFooterMenu() {
        var footerButtons =  document.querySelectorAll('.l-footer .btn--select');
        Array.prototype.slice.call(footerButtons).forEach(function(button) {
            var isShown = false;
            var ddmenu = button.nextElementSibling; 
            button.addEventListener('click', function (e) {
                isShown = !isShown;
                setIsShown(isShown);
            });

            function setIsShown(state) {
                var _state = state;
                toggleClass(ddmenu, 'show', _state);
                toggleClass(button, 'collapsed', !_state);
                toggleStyle(ddmenu, 'display:none', _state);
                toggleAria(button, _state);
            }

        });
        
    };

    function toggleMobileSubMenu() {
        var mobileNavButtons =  document.querySelectorAll('.c-mobile-nav .btn--select');
        Array.prototype.slice.call(mobileNavButtons).forEach(function(button) {
            var isShown = false;
            var ddmenu = button.nextElementSibling; 
            button.addEventListener('click', function (e) {
                isShown = !isShown;
                setIsShown(isShown);
            });

            function setIsShown(state) {
                var _state = state;
                toggleClass(ddmenu, 'show', _state);
                toggleClass(button, 'collapsed', !_state);
                toggleStyle(ddmenu, 'display:none', _state);
                toggleAria(button, _state);
            }

        });
        
    };

    function toggleMobileMenu() {
        var mobileNavButtons =  document.querySelectorAll('.c-top-nav__menu-trigger');
        var body = document.body;
        var modal = document.querySelector('.c-mobile-nav #mobile-navigation');
        Array.prototype.slice.call(mobileNavButtons).forEach(function(button) {
            var isShown = false;
            button.addEventListener('click', function (e) {
                isShown = !isShown;
                setIsShown(isShown);
            });

            function setIsShown(state) {
                var _state = state;
                toggleClass(body, 'modal-open--mobile-nav', _state);
                toggleClass(modal, 'show', _state);
                toggleClass(modal, 'd-block', _state);
                // toggleStyle(modal, 'display:none', _state);
            }

        });
        
    };


    function removeAlert() {
        var alert = document.querySelector('.c-alert');
        var alertCloseBtn = document.querySelector('.c-alert__close');
        alertCloseBtn.addEventListener('click', function(event) {
            if(alert.classList.contains('c-alert__active')) {
                alert.classList.remove('c-alert__active');
            }
        });
    }

    function closeAllDropdownsOnEscape() {
        document.addEventListener('keydown', function(event) {
            if (event.key === 'Escape') {
                console.log('Escape key pressed');



                var ddtoggles = document.querySelectorAll('header .dropdown-toggle');

                Array.prototype.slice.call(ddtoggles).forEach(function(ddtoggle) {
                    var _ddtoggle = ddtoggle;
                    var parent = _ddtoggle.parentElement;
                    var ddmenu = _ddtoggle.nextElementSibling;
                    var _state = false;

                    toggleClass(parent, 'show', _state);
                    toggleClass(ddmenu, 'is-shown', _state);
                    toggleClass(ddmenu, 'is-visible', _state);
                    toggleAria(_ddtoggle, _state);
                    ddmenu.dataset['state'] = String(false);
                    

                });

            }
        });
    }

    function twoClickModal() {
        $('#speed-bump').on('show.bs.modal', function (event) {

            var button = $(event.relatedTarget) // Button that triggered the modal
            console.log(button.attr('href'));
            var link = button.attr('href');
            //var recipient = button.data('whatever') // Extract info from data-* attributes
            // If necessary, you could initiate an AJAX request here (and then do the updating in a callback).
            // Update the modal's content. We'll use jQuery here, but you could use a data binding library or other methods instead.
            var modal = $(this);
            modal.find('.c-speed-bump__link').text(link);
            modal.find('.btn.btn-round').attr('href', link);
            //modal.find('.modal-title').text('New message to ' + recipient)
            //modal.find('.modal-body input').val(recipient)
          })
    }

    function bindEvents() {
        toggleDropdown();
        toggleFooterMenu();
        toggleMobileMenu();
        toggleMobileSubMenu();
        closeAllDropdownsOnEscape();
        removeAlert();
        twoClickModal();
    }

    // Public
    return {
        bindEvents: bindEvents
    };

})(window.document);


/* -------------------------------- Page Load ------------------------------- */

document.addEventListener("DOMContentLoaded", function (event) {
    var readyStateCheckInterval = setInterval(function () {
        if (document.readyState === "complete") {
            clearInterval(readyStateCheckInterval);
            CPRActions.Dropdowns.bindEvents();
        }
    }, 50);
});

