# Google Shopping Id
const data = document.querySelector("[data-sid]").getAttribute("data-sid");

const regex = /catalogid:(\d+)/;
const match = data.match(regex);

if (match && match[1]) {
  const catalogId = match[1];
  console.log(catalogId); // Output: 1467967957255257385
} else {
  console.log('ID not found');
}