 db.productmaterials.aggregate({$lookup:{from:"materials",localField:"materialno",foreignField:"materialno",as:"docs"}},{$unwind:"$docs"},{$lookup:{from:"products",localField:"prodid",foreignField:"prodid",as:"dcs1"}},{$group:{_id:"$prodid",prodname:{$first:"$dcs1.prodname"},total:{$sum:{$multiply:["$docs.unitcost","$number_of_items"]}}}})


 db.products.aggregate({$lookup:{from:"productions",localField:"prodid",foreignField:"prodid",as:"Docs"}},{$unwind:"$Docs"},{$addFields:{Prodname:"$prodname"}},{$group:{_id:"$prodid",prodname:{$first:"$prodname"},total:{$sum:{$multiply:["$price","$Docs.qty"]}}}})
