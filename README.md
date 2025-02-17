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


