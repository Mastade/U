/// remove-reference.js
(function() {
    'use strict';
    
    // Функция удаления элементов
    function removeElements() {
        const elements = document.querySelectorAll('.reference');
        elements.forEach(el => el.remove());
    }

    // Удаляем при загрузке DOM
    if (document.readyState === 'loading') {
        document.addEventListener('DOMContentLoaded', removeElements);
    } else {
        removeElements();
    }

    // Удаляем при полной загрузке страницы
    window.addEventListener('load', removeElements);

    // Наблюдаем за динамически добавляемыми элементами
    const observer = new MutationObserver(function(mutations) {
        mutations.forEach(function(mutation) {
            mutation.addedNodes.forEach(function(node) {
                if (node.nodeType === 1) {
                    if (node.classList && node.classList.contains('reference')) {
                        node.remove();
                    }
                    const refs = node.querySelectorAll('.reference');
                    refs.forEach(function(el) {
                        el.remove();
                    });
                }
            });
        });
    });

    // Запускаем наблюдатель
    if (document.body) {
        observer.observe(document.body, {
            childList: true,
            subtree: true
        });
    } else {
        document.addEventListener('DOMContentLoaded', function() {
            observer.observe(document.body, {
                childList: true,
                subtree: true
            });
        });
    }
})();
