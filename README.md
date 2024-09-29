// If you practise all these problems..
// you will be strong in JS objects manipulations.


// Problem 1 : Part A

// Playing with JSON object"s Values:
//1
// Fluffy sorry, Fluffyy is my fav cat and it has 2 catFriends
// Write a code to get the below details of Fluffyy so that
// I can take him to the vet.
let cat = {
    name: "Fluffy",
    activities: ["play", "eat cat food"],
    catFriends: [
        {
            name: "bar",
            activities: ["be grumpy", "eat sandwich"],
            weight: 8,
            furcolor: "white"
        },
        {
            name: "foo",
            activities: ["sleep", "pre-sleep naps"],
            weight: 3
        },
    ]
};

console.log("Original Cat Object:", cat);

// Task 1: Add height and weight to Fluffy
cat.height = "30 cm"; // Example height
cat.weight = 10; // Example weight
console.log("After adding height and weight:", cat);

// Task 2: Update Fluffy's name to Fluffyy
cat.name = "Fluffyy";
console.log("After updating name:", cat);

// Task 3: List all the activities of Fluffyy's catFriends
const catFriendsActivities = cat.catFriends.map(friend => friend.activities).flat();
console.log("Activities of Fluffyy's catFriends:", catFriendsActivities);

// Task 4: Print the catFriends' names
const catFriendsNames = cat.catFriends.map(friend => friend.name);
console.log("CatFriends' names:", catFriendsNames);

// Task 5: Print the total weight of catFriends
const totalWeight = cat.catFriends.reduce((total, friend) => total + friend.weight, 0);
console.log("Total weight of catFriends:", totalWeight);

// Task 6: Print the total activities of all cats (including Fluffyy)
const totalActivities = cat.activities.length + catFriendsActivities.length;
console.log("Total activities of all cats:", totalActivities);

// Task 7: Add 2 more activities to bar & foo cats
cat.catFriends[0].activities.push("play with string", "chase laser pointer"); // bar
cat.catFriends[1].activities.push("climb tree", "catch mouse"); // foo
console.log("After adding activities to bar & foo:", cat.catFriends);

// Task 8: Update the fur color of bar
cat.catFriends[0].furcolor = "black"; // Changing fur color of bar
console.log("After updating fur color of bar:", cat.catFriends[0]);

// Basic Tasks to play with JSON


// Add height and weight to Fluffy
// Fluffy name is spelled wrongly. Update it to Fluffyy
// List all the activities of Fluffyy"s catFriends.
// Print the catFriends names.
// Print the total weight of catFriends
// Print the total activities of all cats (op:6)
// Add 2 more activities to bar & foo cats
// Update the fur color of bar

// Problem 1 : Part B :

// Iterating with JSON object"s Values

// Below is some information about my car. As you can see, I am not the best driver.
// I have caused a few accidents.
// Please update this driving record so that I can feel better about my driving skills.


let myCar = {
make: "Bugatti",
model: "Bugatti La Voiture Noire",
year: 2019,
accidents: [
{
date: "3/15/2019",
damage_points: "5000",
atFaultForAccident: true
},
{
date: "7/4/2022",
damage_points: "2200",
atFaultForAccident: true
},
{
date: "6/22/2021",
damage_points: "7900",
atFaultForAccident: true
},
]
}

// Question to work on the Iteration with JSON

// 1. Loop over the accidents array and change atFaultForAccident from true to false
myCar.accidents.forEach(accident => {
    if (accident.atFaultForAccident) {
        accident.atFaultForAccident = false;
    }
});

// 2. Print the dates of my accidents
console.log("Dates of my accidents:");
myCar.accidents.forEach(accident => {
    console.log(accident.date);
});
Dates of my accidents:
3/15/2019
6/22/2021

// Real challenges starts here:bowtie:

// Problem 2 :

// Parsing an JSON object"s Values:

// 1.Write a function called "printAllValues" which returns an newArray of all the input object"s values.
// Input (Object):

// let object1 = {name: "RajiniKanth", age: 33, hasPets : false};
// Output:
// ["RajiniKanth", 33, false]

// Sample Function proto:

// let obj = {name : "RajiniKanth", age : 33, hasPets : false};
function printAllValues(obj) {
function printAllValues(obj) {
    return Object.values(obj);
}

// Example usage
let object1 = { name: "RajiniKanth", age: 33, hasPets: false };
let valuesArray = printAllValues(object1);
console.log(valuesArray); // Output: ["RajiniKanth", 33, false]

}


// Problem 3:

// Parsing an JSON object"s Keys:
// Write a function called "printAllKeys" which returns an newArray of all the input object"s keys.
// Example Input:
// {name : "RajiniKanth", age : 25, hasPets : true}
// Example Output:
// ["name", "age", "hasPets"]
// Sample Function proto:

function printAllKeys(obj) {
function printAllKeys(obj) {
    return Object.keys(obj);
}

// Example usage
let object1 = { name: "RajiniKanth", age: 25, hasPets: true };
let keysArray = printAllKeys(object1);
console.log(keysArray); // Output: ["name", "age", "hasPets"]

}


// Problem 4 :

// Parsing an JSON object and convert it to a list:

// Write a function called "convertObjectToList" which converts an object literal into an array of arrays.
// Input (Object):
// let object = {name: "ISRO", age: 35, role: "Scientist"};
// Output:
// [["name", "ISRO"], ["age", 35], ["role", "Scientist"]]
// Sample Function proto:
// let obj = {name: "ISRO", age: 35, role: "Scientist"};
function convertListToObject(obj) {
function convertObjectToList(obj) {
    return Object.entries(obj);
}

// Example usage
let object = { name: "ISRO", age: 35, role: "Scientist" };
let result = convertObjectToList(object);
console.log(result); // Output: [["name", "ISRO"], ["age", 35], ["role", "Scientist"]]

}

// Problem 5: ( 5 mins):

// Parsing a list and transform the first and last elements of it:
// Write a function "transformFirstAndLast" that takes in an array, and returns an object with:
// 1) the first element of the array as the object"s key, and
// 2) the last element of the array as that key"s value.

// Input (Array):
// let array = ["Hi", "I", "am", "Geek"];
// Output:
// let object = {
// HI : "Geek"
// }
// Sample Function proto:
// let arr = ["HI", "I", "am", "a geek"];
function transformFirstAndLast(arr) {
    // Check if the array has at least 2 elements
    if (arr.length < 2) {
        return {}; // Return an empty object if there are not enough elements
    }
    
    const firstElement = arr[0].toUpperCase(); // Get the first element and convert to uppercase
    const lastElement = arr[arr.length - 1]; // Get the last element

    // Create and return the new object
    return {
        [firstElement]: lastElement
    };
}

// Example usage
let array = ["Hi", "I", "am", "Geek"];
let object = transformFirstAndLast(array);
console.log(object); // Output: { HI: "Geek" }


// Problem 6 :

// Parsing a list of lists and convert into a JSON object:
// Write a function "fromListToObject" which takes in an array of arrays, and returns an object with each pair of elements in the array as a key-value pair.
// Input (Array):
// let array = [["make", "Ford"], ["model", "Mustang"], ["year", 1964]];
// Output:
// let object = {
// make : "Ford"
// model : "Mustang",
// year : 1964
// }
// Sample Function proto:
// let arr = [["make", "Ford"], ["model", "Mustang"], ["year", 1964]];
function fromListToObject(arr) {
    let newObject = {}; // Initialize an empty object

    // Iterate over the array of arrays
    arr.forEach(pair => {
        const key = pair[0]; // First element as the key
        const value = pair[1]; // Second element as the value
        newObject[key] = value; // Assign the key-value pair to the object
    });

    return newObject; // Return the constructed object
}

// Example usage
let array = [["make", "Ford"], ["model", "Mustang"], ["year", 1964]];
let object = fromListToObject(array);
console.log(object);
// Output: { make: 'Ford', model: 'Mustang', year: 1964 }

// Problem 7 :

// Parsing a list of lists and convert into a JSON object:
// Write a function called "transformGeekData" that transforms some set of data from one format to another.
// Input (Array):
// let array = [[["firstName", "Vasanth"], ["lastName", "Raja"], ["age", 24], ["role", "JSWizard"]], [["firstName", "Sri"], ["lastName", "Devi"], ["age", 28], ["role", "Coder"]]];

// Output:
// [
// {firstName: "Vasanth", lastName: "Raja", age: 24, role: "JSWizard"},
// {firstName: "Sri", lastName: "Devi", age: 28, role: "Coder"}
// ]

// Sample Function proto:
// let arr= [[["firstName", "Vasanth"], ["lastName", "Raja"], ["age", 24], ["role", "JSWizard"]], [["firstName", "Sri"], ["lastName", "Devi"], ["age", 28], ["role", "Coder"]]];

function transformGeekData(arr) {
    let transformedList = []; // Initialize an empty array to hold the transformed objects

    // Iterate over each inner array
    arr.forEach(innerArray => {
        let obj = {}; // Create a new object for each inner array
        innerArray.forEach(pair => {
            const key = pair[0]; // First element as the key
            const value = pair[1]; // Second element as the value
            obj[key] = value; // Assign the key-value pair to the object
        });
        transformedList.push(obj); // Add the object to the transformed list
    });

    return transformedList; // Return the array of transformed objects
}

// Example usage
let array = [
    [["firstName", "Vasanth"], ["lastName", "Raja"], ["age", 24], ["role", "JSWizard"]],
    [["firstName", "Sri"], ["lastName", "Devi"], ["age", 28], ["role", "Coder"]]
];

let result = transformGeekData(array);
console.log(result);
/*
Output:
[
    { firstName: "Vasanth", lastName: "Raja", age: 24, role: "JSWizard" },
    { firstName: "Sri", lastName: "Devi", age: 28, role: "Coder" }
]
*/

// Problem 8: (10 — 20 mins):

// Parsing two JSON objects and Compare:

// Read this : https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify

// Write an "assertObjectsEqual" function from scratch.
// Assume that the objects in question contain only scalar values (i.e., simple values like strings or numbers).
// It is OK to use JSON.stringify().

// Note: The examples below represent different use cases for the same test. In practice, you should never have multiple tests with the same name.

// Success Case:
// Input:
// let expected = {foo: 5, bar: 6};
// let actual = {foo: 5, bar: 6}
// assertObjectsEqual(actual, expected, "detects that two objects are equal");
// Output:
// Passed

// Failure Case:
// Input:
// let expected = {foo: 6, bar: 5};
// let actual = {foo: 5, bar: 6}
// assertObjectsEqual(actual, expected, "detects that two objects are equal");
// Output:
// FAILED [my test] Expected {"foo":6,"bar":5}, but got {"foo":5,"bar":6}

// let expected = {foo: 5, bar: 6};
// let actual = {foo: 5, bar: 6}
function assertObjectsEqual(actual, expected, testName){
    function assertObjectsEqual(actual, expected, testName) {
        // Convert both objects to JSON strings for comparison
        const actualString = JSON.stringify(actual);
        const expectedString = JSON.stringify(expected);
    
        // Check if the actual string is equal to the expected string
        if (actualString === expectedString) {
            console.log(`Passed: ${testName}`);
        } else {
            console.log(`FAILED [${testName}] Expected ${expectedString}, but got ${actualString}`);
        }
    }
    
    // Example Test Cases
    
    // Success Case
    let expected1 = { foo: 5, bar: 6 };
    let actual1 = { foo: 5, bar: 6 };
    assertObjectsEqual(actual1, expected1, "detects that two objects are equal");
    
    // Failure Case
    let expected2 = { foo: 6, bar: 5 };
    let actual2 = { foo: 5, bar: 6 };
    assertObjectsEqual(actual2, expected2, "detects that two objects are equal");
    
}

// Problem 9 :

// Parsing JSON objects and Compare:

// I have a mock data of security Questions and Answers. You function should take the object and a pair of strings and should return if the quest is present and if its valid answer
// let securityQuestions = [
// {
// question: "What was your first pet"s name?",
// expectedAnswer: "FlufferNutter"
// },
// {
// question: "What was the model year of your first car?",
// expectedAnswer: "1985"
// },
// {
// question: "What city were you born in?",
// expectedAnswer: "NYC"
// }
// ]
function chksecurityQuestions(securityQuestions,question) {
    function chksecurityQuestions(securityQuestions, question, answer) {
        // Iterate through each security question object
        for (let i = 0; i < securityQuestions.length; i++) {
            // Check if the current question matches the input question
            if (securityQuestions[i].question === question) {
                // Check if the expected answer matches the input answer
                return securityQuestions[i].expectedAnswer === answer;
            }
        }
        // Return false if the question is not found
        return false;
    }
    
    // Test Cases
    
    let securityQuestions = [
        {
            question: "What was your first pet's name?",
            expectedAnswer: "FlufferNutter"
        },
        {
            question: "What was the model year of your first car?",
            expectedAnswer: "1985"
        },
        {
            question: "What city were you born in?",
            expectedAnswer: "NYC"
        }
    ];
    
    // Test case 1
    let ques1 = "What was your first pet's name?";
    let ans1 = "FlufferNutter";
    let status1 = chksecurityQuestions(securityQuestions, ques1, ans1);
    console.log(status1); // Output: true
    
    // Test case 2
    let ques2 = "What was your first pet's name?";
    let ans2 = "DufferNutter";
    let status2 = chksecurityQuestions(securityQuestions, ques2, ans2);
    console.log(status2); // Output: false
    
return true/false;
}
// //Test case1:

// let ques = "What was your first pet"s name?";
// let ans  =  "FlufferNutter";
// let status = chksecurityQuestions(securityQuestions, ques, ans);
// console.log(status); // true

// //Test case2:

// let ques = "What was your first pet"s name?";
// let ans  =  "DufferNutter";
// let status = chksecurityQuestions(securityQuestions, ques, ans);
// console.log(status); // flase

// Problem 10 :

// Parsing JSON objects and Compare:
// Write a function to return the list of characters below 20 age

let students = [
    { name: "Siddharth Abhimanyu", age: 21 },
    { name: "Malar", age: 25 },
    { name: "Maari", age: 18 },
    { name: "Bhallala Deva", age: 17 },
    { name: "Baahubali", age: 16 },
    { name: "AAK chandran", age: 23 },
    { name: "Gabbar Singh", age: 33 },
    { name: "Mogambo", age: 53 },
    { name: "Munnabhai", age: 40 },
    { name: "Sher Khan", age: 20 },
    { name: "Chulbul Pandey", age: 19 },
    { name: "Anthony", age: 28 },
    { name: "Devdas", age: 56 }
];

function returnMinors(arr) {
    // Use filter to return an array of students under 20
    return arr.filter(student => student.age < 20);
}

// Output the list of students below the age of 20
console.log(returnMinors(students));
[
    { name: "Maari", age: 18 },
    { name: "Bhallala Deva", age: 17 },
    { name: "Baahubali", age: 16 },
    { name: "Chulbul Pandey", age: 19 }
]

