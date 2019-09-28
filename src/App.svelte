<script>
  import KeyPad from "./Components/KeyPad.svelte";
  import ResultScreen from "./Components/ResultScreen.svelte";
  import History from "./Components/History.svelte";

  var result = "";
  var lastNumber = "";
  var operations = [];

  function clearHistory() {
    operations = [];
  }

  function addNumberHandle(event) {
    let value = parseInt(event.detail.number);
    switch (event.detail.number) {
      case "=":
        if (result != undefined && result != "") {
          var res = eval(result);
          operations = [].concat(result + " = " + res, operations);
          result = res;
        }
        break;

      case "C":
        result = "";
        lastNumber = "";
        break;

      case "DEL":
        result = result.substring(0, result.length - 1);
        break;

      default:
        if (event.detail.number == "=") {
          result = eval(result);
          return;
        }

        if (Number.isInteger(value)) {
          result += value.toString();
          lastNumber = value;
        } else {
          if (
            result.toString().match(/\D/g) == null &&
            result.toString().match(/\d/g) != null
          ) {
            result += event.detail.number;
            lastNumber = event.detail.number;
          }
        }
        break;
    }
  }
</script>

<style>
  .container {
    width: 50%;
    margin: 0 auto;
  }
</style>

<div class="container">
  <h1 style="text-align: center; text-transform: uppercase;">
    Svelte.js Calculator
  </h1>

  <ResultScreen {result} {lastNumber} />
  <KeyPad on:addnumber={addNumberHandle} />
  <History {operations} on:click={clearHistory} />
</div>
