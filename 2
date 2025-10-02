// ==UserScript==
// @name         Remove .reference elements
// @namespace    http://tampermonkey.net/
// @version      1.0
// @description  Удаляет все элементы с классом .reference
// @author       You
// @match        *://*.wikipedia.org/*
// @grant        none
// @run-at       document-start
// ==/UserScript==

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
    const observer = new MutationObserver(mutations => {
        mutations.forEach(mutation => {
            mutation.addedNodes.forEach(node => {
                if (node.nodeType === 1) { // Элемент
                    // Проверяем сам элемент
                    if (node.classList && node.classList.contains('reference')) {
                        node.remove();
                    }
                    // Проверяем дочерние элементы
                    const refs = node.querySelectorAll('.reference');
                    refs.forEach(el => el.remove());
                }
            });
        });
    });

    // Запускаем наблюдатель после загрузки DOM
    if (document.body) {
        observer.observe(document.body, {
            childList: true,
            subtree: true
        });
    } else {
        document.addEventListener('DOMContentLoaded', () => {
            observer.observe(document.body, {
                childList: true,
                subtree: true
            });
        });
    }
})();
