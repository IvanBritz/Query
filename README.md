db.productmaterials.aggregate({$lookup:{from:"materials",localField:"materialno",foreignField:"materialno",as:"docs"}},{$unwind:"$docs"},{$lookup:{from:"products",localField:"prodid",foreignField:"prodid",as:"dcs1"}},{$unwind:"$dcs1"},{$group:{_id:"$prodid",prodname:{$first:"$dcs1.prodname"},total:{$sum:{$multiply:["$docs.unitcost","$number_of_items"]}}}})


db.products.aggregate({$lookup:{from:"productions",localField:"prodid",foreignField:"prodid",as:"Docs"}},{$unwind:"$Docs"},{$group:{_id:"$prodid",prodname:{$first:"$prodname"},total:{$sum:{$multiply:["$price","$Docs.qty"]}}}})



body {
    font-family: Arial, sans-serif;
    margin: 20px;
    padding: 0;
    background-color: #f8f9fa;
}

.container {
    max-width: 800px;
    margin: auto;
    background: white;
    padding: 20px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
}

header {
    text-align: center;
    margin-bottom: 20px;
}

h1 {
    color: #0056b3;
    font-size: 24px;
}

h2, h3 {
    margin-bottom: 10px;
    color: #333;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin-bottom: 20px;
}

table, th, td {
    border: 1px solid #ddd;
    padding: 10px;
    text-align: left;
}

th {
    background-color: #0056b3;
    color: white;
}

strong {
    color: #333;
}









<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>STI Registration Form</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <header>
            <h1>STI COLLEGE DAVAO</h1>
            <p>506 J.P. Laurel Ave., cor. Acacia, Davao City</p>
            <p>Tel. No.: 082 2220914 or 305219</p>
            <h2>Registration and Assessment Form</h2>
        </header>
        
        <section class="student-info">
            <table>
                <tr>
                    <td><strong>Student No:</strong> 02000301172</td>
                    <td><strong>SY & Term:</strong> 2425/2T</td>
                    <td><strong>Program:</strong> BSIT</td>
                </tr>
                <tr>
                    <td><strong>Last Name:</strong> GOLIS</td>
                    <td><strong>First Name:</strong> IVAN</td>
                    <td><strong>Middle Name:</strong> NINAL</td>
                </tr>
                <tr>
                    <td><strong>Year Level:</strong> 3Y2</td>
                </tr>
            </table>
        </section>
        
        <section class="academic">
            <h3>ACADEMIC</h3>
            <table>
                <tr>
                    <th>Course Description</th>
                    <th>Units</th>
                    <th>Class No. / Sec.</th>
                    <th>Days</th>
                    <th>Time</th>
                    <th>Room</th>
                </tr>
                <tr>
                    <td>Web Systems and Technologies</td>
                    <td>3.00</td>
                    <td>16906 / BSIT601</td>
                    <td>MW</td>
                    <td>12:30PM - 1:30PM</td>
                    <td>DINING</td>
                </tr>
                <tr>
                    <td>Management Information Systems</td>
                    <td>3.00</td>
                    <td>16942 / BSIT601</td>
                    <td>MTH</td>
                    <td>1:30PM - 6:00PM</td>
                    <td>COMLAB2</td>
                </tr>
                <tr>
                    <td>Great Books</td>
                    <td>3.00</td>
                    <td>16949 / BSIT601</td>
                    <td>TH</td>
                    <td>6:00PM - 7:30PM</td>
                    <td>403</td>
                </tr>
            </table>
        </section>
        
        <section class="financial">
            <h3>FINANCIAL</h3>
            <table>
                <tr>
                    <th>Charges</th>
                    <th>Amount</th>
                </tr>
                <tr>
                    <td>Tuition Fees</td>
                    <td>27,105.00</td>
                </tr>
                <tr>
                    <td>Other School Fees</td>
                    <td>6,940.00</td>
                </tr>
                <tr>
                    <td>Miscellaneous Fees</td>
                    <td>1,750.00</td>
                </tr>
                <tr>
                    <td><strong>Total Assessment</strong></td>
                    <td><strong>35,795.00</strong></td>
                </tr>
            </table>
        </section>
        
        <section class="payment-schedule">
            <h3>PAYMENT SCHEDULE</h3>
            <table>
                <tr>
                    <th>Date</th>
                    <th>Amount Due</th>
                </tr>
                <tr>
                    <td>Upon Enrollment</td>
                    <td>9,454.40</td>
                </tr>
                <tr>
                    <td>February 17, 2025</td>
                    <td>6,085.15</td>
                </tr>
                <tr>
                    <td>March 25, 2025</td>
                    <td>6,085.15</td>
                </tr>
                <tr>
                    <td>May 02, 2025</td>
                    <td>6,085.15</td>
                </tr>
                <tr>
                    <td>May 30, 2025</td>
                    <td>6,085.15</td>
                </tr>
                <tr>
                    <td><strong>Total Outstanding Balance</strong></td>
                    <td><strong>33,795.00</strong></td>
                </tr>
            </table>
        </section>
    </div>
</body>
</html>


