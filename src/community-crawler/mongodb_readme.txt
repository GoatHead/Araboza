������ �ڷ���:
{
	code: "",
	year: "",
	month: "",
	day: "",
	time: "",
	data: [
		{
			title: ""
			words: [
				{morpheme: "",
				type: ""}
			],
		},

	]
}

db.wordsByTest.aggregate(
    {$unwind: "$data"},
    {$match: {"data.title" : {$regex: /�����/}}},
    {$project: {"title": "$data.title", "words": "$data.words"}}
)