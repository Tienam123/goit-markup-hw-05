«A6» Скрипт модального вікна підключений в HTML окремим файлом modal.js.

Розмітка «B1» Виконана HTML-розмітка всіх елементів макету.

Модальне вікно «D1» Виконана розмітка і оформлення «бекдропа» (темного
напівпрозорого фону) модального вікна.

«D2» «Бекдроп» заповнює 100% висоти і ширини в'юпорту браузера і фіксований в
ньому.

«D3» Виконана розмітка і оформлення модального вікна.

«D4» Модальне вікно вертикально і горизонтально спозиційоване посередині
бекдропа.

«D5» Виконана розмітка і оформлення кнопки закриття модального вікна у верхньому
правому куті.

«D6» Спочатку модальне вікно і бекдроп приховані за допомогою класу is-hidden на
бекдропі, в селекторі якого використовуються властивості visibility, opacity і
pointer-events.

«D7» Якщо прибрати з бекдропа клас is-hidden - з'являється бекдроп і модальне
вікно.

«D8» Поява і приховування модального вікна анімовано за допомогою переходу з
довільним ефектом, наприклад scale або translate, і opacity.

Відкриття/закриття модального вікна Модальне вікно з формою заявки відкривається
по натисканню на кнопку "Замовити послугу". Для того щоб скрипт спрацював,
необхідно додати до розмітки спеціальні атрибути, за якими скрипт шукає
елементи:

data-modal-open - на кнопку відкриття модального вікна. data-modal-close - на
кнопку закриття модального вікна. data-modal - на бекдроп модального вікна.
Після чого, перед закриваючим тегом body додати тег script з посиланням на файл
скрипту для модально вікна. Можна подивитися відео-інструкцію.

<body>
  <!-- Вся твоя розмітка, включно з розміткою модалки -->

  <!-- Ставимо перед закриваючим тегом body -->
  <script src="./js/modal.js"></script>
</body>

Скрипт, який необхідно скопіювати і вставити у файл modal.js.

(() => { const refs = { openModalBtn:
document.querySelector("[data-modal-open]"), closeModalBtn:
document.querySelector("[data-modal-close]"), modal:
document.querySelector("[data-modal]"), };

refs.openModalBtn.addEventListener("click", toggleModal);
refs.closeModalBtn.addEventListener("click", toggleModal);

function toggleModal() { refs.modal.classList.toggle("is-hidden"); } })();
