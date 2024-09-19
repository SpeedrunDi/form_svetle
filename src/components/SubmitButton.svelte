<script>
  export let color = "rgb(44, 47, 71)";
  export let disabled = false;
</script>

<button type="submit" style="background-color: {color}" disabled={disabled}>
  Send
</button>

<style>
    button {
        display: block;
        width: max-content;
        margin: 0 auto;
        padding: 10px 40px;
        border: none;
        border-radius: 50px;
        cursor: pointer;
        color: rgba(255, 255, 255, 0.7);
        font-size: 18px;
    }
    button:hover {
        background: rgb(64, 68, 99)!important;
    }
    button:active {
        background: rgb(44, 47, 71)!important;
    }
    button:disabled {
        background-color: #ccc;
    }

    @media screen and (max-width: 800px) {
        button {
            padding: 7px 35px;
            font-size: 13px;
        }
    }
</style>
