---
date: 2020-11-02 20:07:44
title: Apply

---
<form name="contact" method="POST" data-netlify="true">
  <div class="form-group">
    <label for="fullName">Full Name</label>
    <input type="text" class="form-control" id="fullName" placeholder="Enter name">
  </div>
  <div class="form-group">
    <label for="email">Email Address</label>
    <input type="email" class="form-control" id="email" placeholder="john@email.com">
  </div>
  <div class="form-group">
    <label for="phone">Phone Number</label>
    <input type="text" class="form-control" id="phone" aria-describedby="phoneMsg" placeholder="Phone Number">
    <small id="phoneMsg" class="form-text text-muted">We'll never share your phone number with anyone else.</small>
  </div>
  
  
  
  
  <div class="form-check">
    <input type="checkbox" class="form-check-input" id="exampleCheck1">
    <label class="form-check-label" for="exampleCheck1">Check me out</label>
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>