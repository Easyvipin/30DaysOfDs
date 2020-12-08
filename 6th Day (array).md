## challenge 

```


/* Create a grades object that stores a set of student grades in an object. Provide a
function for adding a grade and a function for displaying the student’s grade average.
 */

class GradeCalc {
  constructor(grades, totalSubject) {
    this.grades = grades;
    this.totalSubject = totalSubject;
    this.average;
  }
  addGrades(grade) {
    if (this.grades.length < this.totalSubject) {
      this.grades.push(grade);
      console.log(this.grades);
    } else {
      console.log(`Sorry you cant add more grade :)`);
    }
  }
  avgGrade() {
    let totalGrade = this.grades.reduce((res, eachM) => res + eachM);
    console.log(totalGrade);
    this.average = Math.round((totalGrade / (this.totalSubject * 100)) * 100);
  }
}
let student1 = new GradeCalc([90, 40, 50, 70], 6);
student1.addGrades();
console.log(student1);
student1.avgGrade();
console.log(student1.average);
/* [90,40 ,50 , 70] */

```
