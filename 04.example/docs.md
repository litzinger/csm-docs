---
title: Example
taxonomy:
    category: docs
---

Given the following settings, Custom System Messages can deliver all ExpressionEngine action and form messages inline with your normal templates. The template code below is the ``/account/sign-in`` template used for normal user logins. It is also defined as the template to use when an error is encountered with the login action. All other non-login related errors in this example will be displayed in the ``/error/index`` template. Note that both Submission Error and General Error fields are required.

<p><img src="http://boldminded.com/assets/images/uploads/csm-settings-example.png" alt="Custom System Messages Settings screenshot" /></p>

## account/sign-in Template

```
{if csm:error == TRUE AND csm:action == 11}
    <div class="form-error-section">
        <div class="error-message">
            <strong>The following errors were encountered:</strong>
            <ul class="error-fields">
                {csm:content}
            </ul>
        </div>
    </div>
{/if}

<div class="grid-row">
    <h3>SIGN IN</h3>
    <p>Don’t have an account yet? <a href="{path='account/register'}">Create an account.</a></p>
    <p><a href="{path='account/forgot-password'}">Forgot your password?</a></p>
</div>

<div class="grid-row">
    {exp:member:login_form return="site/index" form_class="lj-form clearfix"}
        <div class="grid-col size3of6">
            <label for="signin-email">Email Addresss <span class="input-desc">(Username)</span><span class="input-required"> *</span></label>
            <input type="text" id="signin-email" name="username" />
        </div>
        <div class="grid-col size3of6">
            <label for="signin-password">PASSWORD<span class="input-required"> *</span></label>
            <input type="password" id="signin-password" name="password" />
            <button type="submit" name="submit" value="SIGN IN">SIGN IN</button>
        </div>
    {/exp:member:login_form}
</div>
```

## Result

The result of this configuration is the error messages are shown above the login form, instead of on a separate template, and at the same URL. You can still use a separate template if you like. Custom System Messages gives you the flexibility to use whichever template you prefer to display your sites error or success messages.

<p><img src="http://boldminded.com/assets/images/uploads/csm-inline-error.png" alt="Custom System Messages Settings screenshot" /></p>