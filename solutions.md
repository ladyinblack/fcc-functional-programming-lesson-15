## ALTERNATE SOLUTIONS

### Solution 1
```js
function getRating(watchList) {
    // Add your code below this line 
    const averageRating = watchList
        // Use filter to find films directed by Christopher Nolan 
        .filter(film => film.Director === "Christopher Nolan")
        // Use map to convert their ratings from strings to numbers 
        .map(film => Number(film.imdbRating))
        // Use reduce to add together their ratings
        .reduce((sumOfRatings, ratig) => sumOfRatings + rating) / 
        // Divide by the number of Nolan films to get the average rating
        watchList.filter(film => film.Director === "Christopher Nolan").length;
    // Add your code above this line 
    return averageRating;
}

console.log(getRating(watchList));
```

### Solution 2
```js
function getRating(watchList) {
    // Add your code below this line 
    const nolanData = watchList
        .reduce((data, { Director: director, imdbRating: rating }) => {
            if (director === 'Christopher Nolan') {
                data.count++;
                data.sum += Number(rating);
            }
            return data;
        }, { sum: 0, count: 0 });
    const averageRating = nolanData.sum / nolanData.count;
    // Add your code above this line 
    return averageRating;
}

console.log(getRating(watchList));
```

