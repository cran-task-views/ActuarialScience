# June 1

## Dirk Eddelbuettel

- [X] move to books to end, consider shortening the section and putting this into a complementary blog post etc, 
- [X] make a link to the Finance TV strikes me as appropriate 
- [X] nixing (removing) anchors 
- [X] add some words on mortality data for people who are not aware of the good job done by HMD and other national statistics offices. 
- [x] don't wrap lines

## Achim Zeileis

- [X] An introduction is missing. This should set the scene, discuss inclusion/exclusion criteria (see above), etc. You can also include the acknowledgments in this intro.
- [X] You use hard links to other task views. Please avoid that and use the dedicated `r view("...")` tags instead.
- [X] Add a `### Links` section at the end of the .md. You do mention several relevant links in the text (e.g., mortality.org) and listing the important ones in a dedicated section at the end would be useful, I think.
- [x] remove archived packages, https://github.com/cran-task-views/ctv/blob/main/Maintenance.md#CRAN-package-archivals
- [X] If you want to hyperlink DOIs, you can easily do so with the `r doi("...")` tag. 
- [x] You use `> ` quotes for the text that refers to other task views. I don't think this is really necessary. I would put this in regular text.
- [X] the "Mortality databases" section is hard to parse if you miss the package description of `MortalityLaws` in the previous section. I would recommend putting the links into the dedicated `### Links` section at the end of the task view and mention this in the description of the `MortalityLaws` package. 

## Other topics

- [X] Keep an eye on the archived package `MortalityLaws` → unarchived on 2023-08-08.


# July 18

## Achim Zeileis

- [X] The topic field in the header should be in title case: Actuarial Science.
- [X] In the paragraph starting with "The maintainers gratefully acknowledge..." it would be good to also add some encouragement to contribute to the task view with pointers on how this can be done. See some of the other recent task views for examples on how this can be done.
- [X] For the table of contents it's probably easiest to consistently use sentence case. Thus, you need to switch
    Life Insurance → Life insurance
    Non Life Insurance → Non-life insurance
    Note that the latter should also be hyphenated consistently.
- [X] Some elements of the table of contents are out of sync: Related links should be Bibliography and Misc should be Miscellaneous.
- [X] The bibliography is still quite long, maybe it would make sense to cut some of the items that are not directly relevant to R.
- [X] The view(...) tag only adds the hyperlinked name of the task view but does not add the words "task view". Your formulations seem to assume otherwise, please adapt correspondingly.
- [X] At the end of the introductory sentence in Life insurance > Loss modeling about the "Distributions" task view, you might add a sentence like: Here we discuss only those packages that implement distributions particularly designed for actuarial science.
- [X] Please check capitalization also throughout the task view, e.g., incurred or lognormal could probably be lower case? Similarly conditional tail expectation or actuarial measures etc.
