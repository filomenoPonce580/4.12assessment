# 4.12assessment

getProductsBySize()
Update the function so that it assigns products[i] to a variable. Use that variable instead of calling products[i] multiple times.

moreThanThreeProducts()
Update the function so that it doesn't explicitly return true or false.

checkForSizeByName()
Update the function so that the following is true:

products[i] is assigned to a variable.

It returns false early if there is no product.

It does not explicitly return true or false when checking for the size.


//code
/*
  Modify each function below to continue working with the suggested syntax.
  
  When a function's parameters reference `products`, it is referring to an array of objects. Each object has the following shape:
   {
     name: "Slip Dress",
     priceInCents: 8800,
     availableSizes: [ 0, 2, 4, 6, 10, 12, 16 ]
   }
*/

function getProductsBySize(products, size) {
  const result = [];
  for (let i = 0; i < products.length; i++) {
    for (let j = 0; j < products[i].availableSizes.length; j++) {
      if (products[i].availableSizes[j] === size) {
        result.push(products[i]);
      }
    }
  }

  return result;
}

function moreThanThreeProducts(products) {
  if (products.length < 4) {
    return false;
  } else {
    return true;
  }
}

function checkForSizeByName(products, name, size) {
  let product = null;
  for (let i = 0; i < products.length; i++) {
    if (products[i].name === name) {
      product = products[i];
    }
  }

  if (product) {
    if (product.availableSizes.includes(size)) {
      return true;
    } else {
      return false;
    }
  } else {
    return false;
  }
}

module.exports = {
  getProductsBySize,
  moreThanThreeProducts,
  checkForSizeByName,
};
