<script>
  import InputField from './InputField.svelte';
  import Checkbox from './Checkbox.svelte';
  import SubmitButton from './SubmitButton.svelte';

  let name = '';
  let company = '';
  let email = '';
  let phone = '';
  let subject = '';
  let message = '';
  let consent = false;

  let errors = {};

  function validateForm() {
    errors = {};
    if (!name) errors.name = "Name is required";
    if (!company) errors.company = "Company is required";
    if (!email || !/^\S+@\S+\.\S+$/.test(email)) errors.email = "Valid email is required";
    if (!message) errors.message = "Message is required";
    if (!consent) errors.consent = "You must accept the terms";
    return Object.keys(errors).length === 0;
  }

  function handleSubmit() {
    if (validateForm()) {
      alert("Form submitted successfully!");
      // Реализация отправки формы
    }
  }
</script>

<form on:submit|preventDefault={handleSubmit}>
  <p class="sub-title">For business enquiries please use the form below</p>
  <p class="required-text">*Required</p>
  <InputField label="Name" bind:value={name} required error={errors.name} />
  <InputField label="Company" bind:value={company} required error={errors.company} />
  <InputField label="E-mail" bind:value={email} required type="email" error={errors.email} />
  <InputField label="Phone" bind:value={phone} type="tel" />
  <InputField label="Subject" bind:value={subject} />
  <InputField label="Message" bind:value={message} required type="textarea" error={errors.message} />
  <Checkbox bind:checked={consent} />
  {#if errors.consent}
    <span class="error-message">{errors.consent}</span>
  {/if}
  <SubmitButton color="rgb(44, 47, 71)" />
</form>

<style>
    form {
        border-radius: 27px;
        box-shadow: 0 0 50px 0 rgba(0, 0, 0, 0.7);
        background: rgb(23, 25, 41);
        padding: 40px 45px;
        max-width: 300px;
        width: 100%;
        margin: 0 auto auto;
        color: white;
    }

    .sub-title {
        max-width: 240px;
        margin: 0 auto 11px;
        text-align: center;
    }

    .required-text {
        margin: 0 0 10px;
        color: rgb(121, 126, 163);
        font-size: 15px;
        font-weight: 300;
        text-align: center;
    }

    @media screen and (max-width: 800px) {
        form {
            padding: 30px 35px;
            max-width: 220px;
        }

        .sub-title {
            max-width: 200px;
            margin: 0 auto 8px;
        }

        .required-text {
            margin: 0 0 7px;
            font-size: 12px;
        }
    }
</style>
