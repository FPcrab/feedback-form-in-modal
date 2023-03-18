# feedback-form-in-modal


Данная форма - это проект с исходным кодом, который расположен на GitHub 



Основные действия по подключению формы обратной связи.

1. Добавить кнопку или ссылку для вызова модального окна.





<!-- Кнопка, открывающая модальное окно -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#feedbackFormModal">
	Открыть форму в модальном окне
</button>




2. Создать модальное окно и поместить в него HTML код формы обратной связи.





<!-- Форма обратной связи в модальном окне -->
<div class="modal" id="feedbackFormModal" tabindex="-1" role="dialog" aria-labelledby="myModalLabel">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="myModalLabel">Форма обратной связи</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">×</span>
        </button>
      </div>
      <div class="modal-body">

        <!-- Форма обратной связи -->
        <form id="feedbackForm" action="/feedback/process/process.php" enctype="multipart/form-data" novalidate>
          <div class="form-row">
            <div class="col-sm-6">
              <!-- Имя пользователя -->
              <div class="form-group">
                <label for="name" class="control-label">Имя</label>
                <input id="name" type="text" name="name" class="form-control" value="" placeholder="Имя" minlength="2" maxlength="30" required="required">
                <div class="invalid-feedback"></div>
              </div>
            </div>
            <div class="col-sm-6">
              <!-- Email пользователя -->
              <div class="form-group">
                <label for="email" class="control-label">Email-адрес</label>
                <input id="email" type="email" name="email" required="required" class="form-control" value="" placeholder="Email-адрес">
                <div class="invalid-feedback"></div>
              </div>
            </div>
          </div>
          <!-- Сообщение пользователя -->
          <div class="form-group">
            <label for="message" class="control-label">Сообщение (не менее 20 символов)</label>
            <textarea id="message" name="message" class="form-control" rows="3" placeholder="Сообщение (не менее 20 символов)" minlength="20" maxlength="500" required="required"></textarea>
            <div class="invalid-feedback"></div>
          </div>
          <!-- Изображения -->
          <div class="form-group attachments">
            <div>При необходимости прикрепите к сообщению изображения (до <span class="countFiles"></span>):
            </div>
            <div class="mb-1 text-muted">
              <small>максимальный размер одного изобржения 512 Кбайт</small>
            </div>
            <div class="alert alert-warning d-none mb1"><small class="attachments-error"></small></div>
              <div class="custom-file">
                <input type="file" name="attachment[]" class="custom-file-input" id="customFile1">
                <label class="custom-file-label" for="customFile1">Выбреите файл...</label>
                <div class="invalid-feedback"></div>
              </div>
          </div>
          <!-- Капча -->
          <div class="form-group captcha">
            <img class="img-captcha" src="/feedback/captcha/captcha.php" data-src="/feedback/captcha/captcha.php">
            <div class="btn btn-light refresh-captcha">Обновить</div>
            <div class="form-group">
              <label for="captcha" class="control-label">Код, показанный на изображении</label>
              <input type="text" name="captcha" maxlength="6" required="required" id="captcha" class="form-control captcha" placeholder="******" autocomplete="off" value="">
              <div class="invalid-feedback"></div>
            </div>
          </div>
          <!-- Пользовательское солашение -->
          <div class="form-group">
            <div class="custom-control custom-checkbox">
              <input type="checkbox" name="agree" class="custom-control-input" id="customCheck">
              <label class="custom-control-label" for="customCheck">Нажимая кнопку, я принимаю условия <a href="#">Пользовательского соглашения</a> и даю своё согласие на обработку моих персональных данных, в соответствии с Федеральным законом от 27.07.2006 года №152-ФЗ «О персональных данных».</label>
            </div>
          </div>
          <!-- Сообщение -->
          <div class="alert alert-danger form-error d-none">
            Произошли ошибки! Исправьте их и отправьте форму ещё раз.
          </div>
          <!-- Индикация загрузки данных формы на сервер -->
          <div class="progress mb-2 d-none">
            <div class="progress-bar progress-bar-success progress-bar-striped" role="progressbar" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100" style="width: 0">
              <span class="sr-only">0%</span>
            </div>
          </div>
          <!-- Кнопка для отправки формы -->
          <button type="submit" class="btn btn-primary float-right" disabled="disabled">Отправить сообщение</button>
        </form>
                
        <!-- Сообщение об успешной отправки формы -->
        <div class="alert alert-success form-success mb-0 d-none">Форма успешно отправлена. Нажмите на <a class="form-success-link" href="#">ссылку</a>, чтобы отправить ещё одно сообщение.</div>
      </div>
    </div>
  </div>
</div>






3. Подключить стили и скрипты используемых компонентов (jQuery, Bootstrap) и самой формы (main.css, main.js):

<!-- Подключение CSS файлов -->
<link rel="stylesheet" href="/feedback/vendors/bootstrap/css/bootstrap.min.css">
<link rel="stylesheet" href="/feedback/css/main.css">

<!-- Подключение JS файлов -->
<script src="/feedback/vendors/jquery/jquery-3.3.1.min.js"></script>
<script src="/feedback/vendors/bootstrap/js/bootstrap.min.js"></script>
<script src="/feedback/js/main.js"></script>
