<script>
  export let checked = false;
</script>

<div class="checkbox-wrapper">
  <label class="checkbox-label" for="checkbox">
    <input id="checkbox" type="checkbox" required bind:checked />
    <span class="checkbox-icon"></span>
    <span class="checkbox-text">I accept <span class="checkbox-text-click">Terms and Privacy Policy</span></span>
  </label>
</div>

<style>
    .checkbox-wrapper {
        display: flex;
        align-items: center;
        margin-bottom: 20px;
    }
    .checkbox-label {
        display: inline-block;
        position: relative;
        padding-left: 40px;
        cursor: pointer;
        line-height: 30px;
    }
    input[type="checkbox"] {
        position: absolute;
        opacity: 0;
        cursor: pointer;
    }
    .checkbox-icon {
        position: absolute;
        top: 0;
        left: 0;
        width: 30px;
        height: 30px;
        border-radius: 8px;
        background: rgb(44, 47, 71);
        transition: background-color 0.3s, border-color 0.3s;
    }
    input[type="checkbox"]:checked ~ .checkbox-icon::after {
        content: "";
        position: absolute;
        left: 11px;
        top: 6px;
        width: 6px;
        height: 12px;
        border: solid white;
        border-width: 0 2px 2px 0;
        transform: rotate(45deg);
    }
    .checkbox-text {
        font-size: 15px;
        color: rgb(121, 126, 163);
    }
    .checkbox-text-click {
        font-size: 15px;
        color: rgb(185, 190, 230);
        text-decoration-line: underline;
    }

    @media screen and (max-width: 800px) {
        .checkbox-wrapper {
            margin-bottom: 12px;
        }
        .checkbox-label {
            padding-left: 30px;
            cursor: pointer;
            line-height: 20px;
        }
        .checkbox-icon {
            position: absolute;
            top: 0;
            left: 0;
            width: 20px;
            height: 20px;
        }
        input[type="checkbox"]:checked ~ .checkbox-icon::after {
            content: "";
            position: absolute;
            left: 7px;
            top: 4px;
            width: 4px;
            height: 8px;
        }
        .checkbox-text {
            font-size: 12px;
        }
        .checkbox-text-click {
            font-size: 12px;
        }
    }
</style>
