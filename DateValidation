
// Express.js

  // include all months
  let months = [
  {name: "january"}, {altNames:[jan]}, feburary:{ [feb], mar, apr, may, jun, jul, aug, sep, oct, nov, dec
  ];

  const sanitizedPayload = {
          // require each part of date seperatly
          // everything gets to be a string! :D
          date: {year: req.body.date.year.toString(), month: req.body.date.month.toString(), day: req.body.date.day.toString(),},
          breakfastMenu: req.body.breakfastMenu.toString(),
          lunchMenu: req.body.lunchMenu.toString(),
          dinnerMenu: req.body.dinnerMenu.toString(),
      }

      //TODO: get an actual validation library to check if empty, trim, and escape

      let formattedDate;

      // if the primary key is missing, empty, or doesn't parse as a date then respond with an error
      // this insures that any date set via the api will be consistent
      if (sanitizedPayload.date.year != '' && sanitizedPayload.date.month != '' && sanitizedPayload.date.month != 0 && sanitizedPayload.date.day != '' && sanitizedPayload.date.day != 0)
      {
          let date = Date.parse((sanitizedPayload.date.day + ' ' + sanitizedPayload.date.month + '' + sanitizedPayload.date.year).toString());
          console.log(date);
          formattedDate = new Date(date);
          console.log(formattedDate);
          formattedDate = formattedDate.toISOString();
          formattedDate = formattedDate.substring(0, formattedDate.indexOf('T'));
          console.log(formattedDate);
      }
      else {
          return res.status(400).json({
              message: "the date is invalid",
              error: "unable to parse",
              date: sanitizedPayload.date,
          });
      }
