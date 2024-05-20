// The function load contents of other webpages
function ShowContent(pageName) {    
  fetch(pageName + ".html")
    .then((response) => {
      if (!response.ok) {
        throw new Error("Failed to load page");
      }
      return response.text();
    })
    .then((html) => {
      document.getElementById("content").innerHTML = html;
    })
    .catch((error) => console.error("Failed to load page: ", error));

  // Update active link and navbar color
  const links = document.querySelectorAll('#navbar a');
  links.forEach(link => {
    link.classList.remove('active'); // Remove active class from all links
  });
  const activeLink = document.querySelector(`#navbar a[href="#"][onclick="ShowContent('${pageName}')"]`);
  if (activeLink) {
    activeLink.classList.add('active'); // Add active class to the current link
  }
}
window.addEventListener("DOMContentLoaded",function(){
  ShowContent('home');
})