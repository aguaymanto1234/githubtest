function calculateInterest() {
    // Obtener los valores ingresados por el usuario
    const principal = parseFloat(document.getElementById("principal").value);
    const rate = parseFloat(document.getElementById("rate").value) / 100;
    const time = parseFloat(document.getElementById("time").value);

    // Verificar que todos los valores sean válidos
    if (isNaN(principal) || isNaN(rate) || isNaN(time)) {
        document.getElementById("result").innerHTML = "Por favor, ingresa valores válidos.";
        return;
    }

    // Cálculo de interés compuesto
    const compoundInterest = principal * Math.pow((1 + rate), time);
    const interestEarned = compoundInterest - principal;

    // Mostrar el resultado en el HTML
    document.getElementById("result").innerHTML = `
        <strong>Resultado:</strong><br>
        Monto Final: $${compoundInterest.toFixed(2)}<br>
        Interés Ganado: $${interestEarned.toFixed(2)}
    `;
}
