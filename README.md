// Smooth scrolling for internal links
document.addEventListener('DOMContentLoaded', function(){
  document.querySelectorAll('a[href^="#"]').forEach(function(anchor){
    anchor.addEventListener('click', function(e){
      var href = this.getAttribute('href');
      if(href.length > 1){
        e.preventDefault();
        document.querySelector(href).scrollIntoView({behavior:'smooth', block:'start'});
        // close mobile nav
        if(window.innerWidth < 900){
          document.getElementById('nav').style.display = 'none';
        }
      }
    });
  });

  // year
  document.getElementById('year').textContent = new Date().getFullYear();

  // mobile toggle
  var navToggle = document.getElementById('nav-toggle');
  navToggle.addEventListener('click', function(){
    var nav = document.getElementById('nav');
    if(nav.style.display === 'flex') nav.style.display = 'none';
    else nav.style.display = 'flex';
  });
});

// demo contact form handler
function handleSubmit(e){
  e.preventDefault();
  var form = e.target;
  var name = form.name.value.trim();
  var email = form.email.value.trim();
  if(!name || !email){ alert('Please fill required fields.'); return false; }
  alert('Thanks ' + name + '! This is a demo form. Replace with your backend or form provider.');
  form.reset();
  return false;
}![IMG_1441](https://github.com/user-attachments/assets/eb0e0f79-05bb-44e8-9927-443ecc73b364)
