<script>
    Validator({
        form: '#form-1',
        formGroupSelector: '.container__login-input-item',
        errorSelector: '.form-message',
        rules: [
            Validator.isRequired('#fullname', 'Vui lòng nhập tên đầy đủ của bạn'),
            Validator.minLength('#fullname', 6),
            Validator.isRequired('#user', 'Vùi lòng nhập tài khoản của bạn'),
            Validator.minLength('#user', 5),
            Validator.isRequired('#email', 'Vui lòng nhập email của bạn'),
            Validator.isEmail('#email'),
            Validator.isRequired('#password', 'Vui lòng nhập mật khẩu của bạn'),
            Validator.minLength('#password', 5),
            Validator.isRequired('#password_confirmation','Vui lòng nhập mật khẩu của bạn'),
            Validator.isComfirmed('#password_confirmation', function() {
                return document.querySelector('#form-1 #password').value
            }, 'Mật khẩu nhập lại không chính xác')
        ],
        onSubmit: function(data) {
            // Call Api
            console.log(data)
        }
    });
</script>