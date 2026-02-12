<section id="registration">
  <h2>Register Now</h2>
  <p>Fill in your details and click the button to send your registration directly via WhatsApp.</p>

  <form id="whatsappForm">
    <div class="form-group">
      <label for="name">Full Name:</label>
      <input type="text" id="name" name="name" required>
    </div>
    <div class="form-group">
      <label for="phone">Phone Number:</label>
      <input type="tel" id="phone" name="phone" required>
    </div>
    <div class="form-group">
      <label for="startdate">Preferred Start Date:</label>
      <input type="date" id="startdate" name="startdate" required>
    </div>
    <div class="form-group">
      <input type="checkbox" id="terms" name="terms" required>
      <label for="terms">I have read and agree to the Terms & Conditions</label>
    </div>
    <div class="form-group">
      <label for="payment">Payment Method:</label>
      <select id="payment" name="payment" required>
        <option value="mpesa">M-Pesa</option>
        <option value="bank">Bank Transfer</option>
        <option value="cash">Cash</option>
      </select>
    </div>
    <button type="button" onclick="sendWhatsApp()">Register & Pay via WhatsApp</button>
  </form>

  <div class="payment-info">
    <h3>Payment Instructions:</h3>
    <p><strong>M-Pesa Paybill:</strong> 123456 (Account: Simon Wambua)</p>
    <p>After payment, confirm via WhatsApp at <strong>+254706XXXXXX</strong></p>
  </div>
</section>

<script>
function sendWhatsApp() {
  const name = document.getElementById('name').value;
  const phone = document.getElementById('phone').value;
  const startdate = document.getElementById('startdate').value;
  const terms = document.getElementById('terms').checked;
  const payment = document.getElementById('payment').value;

  if(!name || !phone || !startdate || !terms || !payment){
    alert("Please complete all fields and agree to the terms.");
    return;
  }

  const message = `Hello Simon,%0AI want to register for the 8-week Transformation Program.%0AName: ${name}%0APhone: ${phone}%0APreferred start date: ${startdate}%0APayment method: ${payment}`;
  const whatsappNumber = "254706XXXXXX"; // Replace with your WhatsApp number
  const url = `https://wa.me/${whatsappNumber}?text=${message}`;
  window.open(url, "_blank");
}
</script>
