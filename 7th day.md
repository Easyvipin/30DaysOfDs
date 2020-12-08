## challenge (array)

```
Create functions to display the monthly aver‐
age, a specific week’s average, and all the weeks’ averages.
 */

class DataTemps {
  constructor(data, average) {
    this.data = data;
    this.average = average;
  }
  weeklyAverage() {
    console.log(this.data);
  }
  addTemps(weekNo, temp) {
    if (this.data.length > weekNo - 1) {
      if (this.data[weekNo - 1].length < 7) {
        this.data[weekNo - 1].push(temp);
      } else {
        console.log("data is already available");
      }
    } else {
      console.log("week no is invalid");
    }
  }
  calAverage(period) {
    let total = 0;
    let weekAvg = [];

    /* monthly  and all week*/
    if (period === "MON") {
     
      for (let i of this.data) {
        for (let j of i) {
          total += j;      
        }
        weekAvg.push(total / i.length);
        total = 0 ; 
      }
      this.average = Math.round(weekAvg.reduce((calc,res)=>calc+res) / this.data.length);
    for(let i of weekAvg){
     console.log(Math.round(i));
   }
    }

    /* specific week */
   if(Number.isInteger(period)){
    for (let j of this.data[period - 1]) {
      total += j;
    }
    console.log(Math.round(total / this.data[period - 1].length))
   }
  }

}

const jan = new DataTemps([
  [10, 50, 30, 30, 20, 21, 19],
  [30, 40, 20, 31, 21, 30, 21],
  [19, 12, 34, 21, 43, 54, 12],
  []
]);
jan.addTemps(4, 21);
jan.addTemps(4, 21);
jan.addTemps(4, 21);
jan.addTemps(4, 21);
jan.addTemps(4, 20);
jan.addTemps(4, 26);
jan.addTemps(4, 29);

jan.calAverage("MON");
jan.calAverage(3);
console.log(jan);

```
