let expensesArray=[];
function expenseTracker(str,int){
let objectTemplate = {
  expense:str,
  amount:int
}
  expensesArray.push(objectTemplate)
return expensesArray
}
let income = 0;
function updIncome(int){
  income=int;
  return income;
}
function remainingBalance(array){
  let currentBalance = income;
  let remainingBalances=0;
  let expensesArray=[];
  for(let i of array){
    expensesArray.push(i["expense"])
    currentBalance-= i["amount"]
  }
  if(currentBalance<income*0.1){
    return` Remaining balance: ${currentBalance} please revisit your expenditure your current expenses are: ${expensesArray}`
  }
  else{return` Congratulations your remaining balance is: ${currentBalance} your expenses: ${expensesArray} I recommend you save your remaining balance in case of a rainy day`
  }
}

console.log(expenseTracker("Subscriptions",1000))
console.log(updIncome(25000))
console.log(remainingBalance(expensesArray))
