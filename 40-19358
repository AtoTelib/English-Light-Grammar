s(s(NOUNPART,VERBPART), Sentence, EmptyList):-
    noun_part_cases(NOUNPART, Sentence, VerbPart),
    verb_cases(VERBPART, VerbPart, EmptyList).

s(s(NOUNPART), Sentence, EmptyList):-
    noun_part_cases(NOUNPART, Sentence, EmptyList).

s(q(Wh_Question, V, NOUNPART), Question, EmptyList):-
    question(Wh_Question, Question, Remaining),
    verb_instance(V, Remaining, Remaining1),
    noun_part_cases_in_question(NOUNPART, Remaining1, EmptyList).    

determiner_part_cases((Determiner, AdjectivePart), Sentence, Remaining):-
    determiner_instance(Determiner, Sentence, Adjective_Sentence),
    adjective_part(AdjectivePart, Adjective_Sentence, Remaining).
    
determiner_part_cases(Determiner, Sentence, Remaining):-
    determiner_instance(Determiner, Sentence, Remaining).

determiner_part_cases(AdjectivePart, Sentence, Remaining):-
    adjective_part(AdjectivePart, Sentence, Remaining).

adjective_part((Adjective_instance, AdjectivePart), Sentence, Noun_Part):-
    adjective_instance(Adjective_instance, Sentence, Remaining),
    adjective_part(AdjectivePart, Remaining, Noun_Part).
    
adjective_part(Adjective_instance, Sentence, Noun_Part):-
    adjective_instance(Adjective_instance, Sentence, Noun_Part).           

noun_part_cases((Determiner, Noun_Part1), Sentence, Noun_Part):-
    determiner_part_cases(Determiner, Sentence, Remaining),
    noun_cases(Noun_Part1, Remaining, Noun_Part).

noun_part_cases(Noun_Part1, Sentence, Noun_Part):-
    noun_cases(Noun_Part1, Sentence, Noun_Part).

noun_cases((Noun, PREPOSITION, Noun_Part_Cases), Sentence, EndofSentence):-
    noun_instance(Noun,Sentence, Remaining1),
    preposition_instance(PREPOSITION,Remaining1, Remaining12),
    noun_part_cases(Noun_Part_Cases, Remaining12, EndofSentence).

noun_cases((Noun, Conjunction, Verb_Part, Noun_Part_Cases), Sentence, Remaining12):-
    noun_instance(Noun, Sentence, Remaining1),
    conjunction_instance(Conjunction, Remaining1, Remaining14),
    verb_cases(Verb_Part, Remaining14, Remaining13),
    noun_part_cases(Noun_Part_Cases, Remaining13, Remaining12).

noun_cases((Noun, Conjunction, Noun_Part_Cases, Verb_Part),Sentence, Remaining13):-
    noun_instance(Noun, Sentence, Remaining1),
    conjunction_instance(Conjunction, Remaining1, Remaining14),
    noun_part_cases(Noun_Part_Cases, Remaining14, Remaining12),
    verb_cases(Verb_Part, Remaining12, Remaining13).

noun_cases((Noun, Conjunction, Verb_Part), Sentence, VerbPart):-
    noun_instance(Noun, Sentence, Remaining1),
    conjunction_instance(Conjunction, Remaining1, Remaining14),
    verb_cases(Verb_Part, Remaining14, VerbPart).  

noun_cases((Noun, Conjunction, Noun_Part_Cases), Sentence, VerbPart):-
    noun_instance(Noun, Sentence, Remaining1),
    conjunction_instance(Conjunction, Remaining1, Remaining14),
    noun_part_cases(Noun_Part_Cases, Remaining14, VerbPart). 

noun_cases((Noun, Noun_Part_Cases), Sentence, Verb_Part):-
    noun_instance(Noun, Sentence, Remaining1),
    noun_part_cases(Noun_Part_Cases, Remaining1, Verb_Part). 

noun_cases((Noun), Sentence, Verb_Part):-
    noun_instance(Noun, Sentence, Verb_Part).                  

adverb_cases((Adverb, Adverb_part), Sentence, VerbPart):-
    adverb_instance(Adverb, Sentence, Remaining),
    adverb_cases(Adverb_part, Remaining, VerbPart).
    
adverb_cases(Adverb, Sentence, Verb_Part):-
    adverb_instance(Adverb, Sentence, Verb_Part).

verb_cases((Adverb_part, Verb_Part), AdverbPart, EmptyList):-
    adverb_cases(Adverb_part, AdverbPart, Remaining),
    verb_cases(Verb_Part, Remaining, EmptyList).

verb_cases((Verb, Conjunction, Verb_Part), VerbPart, EmptyList):-
    verb_instance(Verb, VerbPart, Remaining1),
    conjunction_instance(Conjunction, Remaining1, Remaining14),
    verb_cases(Verb_Part, Remaining14, EmptyList).

verb_cases((Verb, Noun_Part_Cases), VerbPart, EmptyList):-
    verb_instance(Verb, VerbPart, Remaining),
    noun_part_cases(Noun_Part_Cases, Remaining, EmptyList).

verb_cases((Verb), VerbPart, EmptyList):-
    verb_instance(Verb, VerbPart, EmptyList).  

noun_part_cases_in_question((Determiner, Noun_Part1), Sentence, Noun_Part):-
    determiner_part_cases(Determiner, Sentence, Remaining),
    noun_cases_in_question(Noun_Part1, Remaining, Noun_Part).

noun_part_cases_in_question(Noun_Part1, Sentence, Noun_Part):-
    noun_cases_in_question(Noun_Part1, Sentence, Noun_Part).

noun_cases_in_question((Noun_Part1, PREPOSITION, Noun_Part_Cases), Sentence, EndofSentence):-
    noun_instance(Noun_Part1,Sentence, Remaining1),
    preposition_instance(PREPOSITION,Remaining1, Remaining12),
    noun_part_cases_in_question(Noun_Part_Cases, Remaining12, EndofSentence).

noun_cases_in_question((NounPart, Conjunction, Verb_Part, Noun_Part_Cases), Sentence, Remaining12):-
    noun_instance(NounPart, Sentence, Remaining1),
    conjunction_instance(Conjunction, Remaining1, Remaining14),
    verb_cases_in_question(Verb_Part, Remaining14, Remaining13),
    noun_part_cases_in_question(Noun_Part_Cases, Remaining13, Remaining12).

noun_cases_in_question((NounPart, Conjunction, Noun_Part_Cases, Verb_Part),Sentence, Remaining13):-
    noun_instance(NounPart, Sentence, Remaining1),
    conjunction_instance(Conjunction, Remaining1, Remaining14),
    noun_part_cases_in_question(Noun_Part_Cases, Remaining14, Remaining12),
    verb_cases_in_question(Verb_Part, Remaining12, Remaining13).

noun_cases_in_question((NounPart, Conjunction, Verb_Part), Sentence, VerbPart):-
    noun_instance(NounPart, Sentence, Remaining1),
    conjunction_instance(Conjunction, Remaining1, Remaining14),
    verb_cases_in_question(Verb_Part, Remaining14, VerbPart).  

noun_cases_in_question((NounPart, Conjunction, Noun_Part_Cases), Sentence, VerbPart):-
    noun_instance(NounPart, Sentence, Remaining1),
    conjunction_instance(Conjunction, Remaining1, Remaining14),
    noun_part_cases_in_question(Noun_Part_Cases, Remaining14, VerbPart). 

noun_cases_in_question((NounPart, Noun_Part_Cases), Sentence, VerbPart):-
    noun_instance(NounPart, Sentence, Remaining1),
    noun_part_cases_in_question(Noun_Part_Cases, Remaining1, VerbPart). 

noun_cases_in_question(NounPart, Sentence, VerbPart):-
    noun_instance(NounPart, Sentence, VerbPart).                  

noun_cases_in_question(Verb_Part, Sentence, VerbPart):-
    verb_cases_in_question(Verb_Part, Sentence, VerbPart). 

verb_cases_in_question((Adverb_part, Verb_Part), AdverbPart, EmptyList):-
    adverb_cases(Adverb_part, AdverbPart, Remaining),
    verb_cases_in_question(Verb_Part, Remaining, EmptyList).

verb_cases_in_question((Verb, Conjunction, Verb_Part), VerbPart, EmptyList):-
    infinitive_verb_instance(Verb, VerbPart, Remaining1),
    conjunction_instance(Conjunction, Remaining1, Remaining14),
    verb_cases_in_question(Verb_Part, Remaining14, EmptyList).

verb_cases_in_question((Verb, Noun_Part_Cases), VerbPart, EmptyList):-
    infinitive_verb_instance(Verb, VerbPart, Remaining),
    noun_part_cases_in_question(Noun_Part_Cases, Remaining, EmptyList).

verb_cases_in_question((Verb,PREPOSITIONS, Noun_Part_Cases), VerbPart, EmptyList):-
    infinitive_verb_instance(Verb, VerbPart, Remaining),
    preposition_instance(PREPOSITIONS, Remaining, Remaining1),
    noun_part_cases_in_question(Noun_Part_Cases, Remaining1, EmptyList).

verb_cases_in_question((Verb), VerbPart, EmptyList):-
    infinitive_verb_instance(Verb, VerbPart, EmptyList).

noun_instance(noun(boy), [boy|Remaining], Remaining).
noun_instance(noun(box), [box|Remaining], Remaining).
noun_instance(noun(school), [school|Remaining], Remaining).
noun_instance(noun(man), [man|Remaining], Remaining).
noun_instance(noun(shed), [shed|Remaining], Remaining).
noun_instance(noun(student), [student|Remaining], Remaining).
noun_instance(noun(lecturer), [lecturer|Remaining], Remaining).
noun_instance(noun(researcher), [researcher|Remaining], Remaining).
noun_instance(noun(grade), [grade|Remaining], Remaining).
noun_instance(noun(book), [book|Remaining], Remaining).
noun_instance(noun(students), [students|Remaining], Remaining).
noun_instance(noun(professors), [professors|Remaining], Remaining).
noun_instance(noun(researchers), [researchers|Remaining], Remaining).
noun_instance(noun(girl), [girl|Remaining], Remaining).
noun_instance(noun(room), [room|Remaining], Remaining).
noun_instance(noun(envelope), [envelope|Remaining], Remaining).
noun_instance(noun(woman), [woman|Remaining], Remaining).
noun_instance(noun(building), [building|Remaining], Remaining).
noun_instance(noun(professor), [professor|Remaining], Remaining).
noun_instance(noun(scientist), [scientist|Remaining], Remaining).
noun_instance(noun(tree), [tree|Remaining], Remaining).
noun_instance(noun(door), [door|Remaining], Remaining).
noun_instance(noun(assignment), [assignment|Remaining], Remaining).
noun_instance(noun(lecturers), [lecturers|Remaining], Remaining).
noun_instance(noun(scientists), [scientists|Remaining], Remaining).

determiner_instance(deter(a), [a|Remaining], Remaining).
determiner_instance(deter(some), [some|Remaining], Remaining).
determiner_instance(deter(that), [that|Remaining], Remaining).
determiner_instance(deter(an), [an|Remaining], Remaining).
determiner_instance(deter(this), [this|Remaining], Remaining).
determiner_instance(deter(few), [few|Remaining], Remaining).
determiner_instance(deter(those), [those|Remaining], Remaining).
determiner_instance(deter(these), [these|Remaining], Remaining).
determiner_instance(deter(every), [every|Remaining], Remaining).
determiner_instance(deter(the), [the|Remaining], Remaining).
determiner_instance(deter(many), [many|Remaining], Remaining).


adverb_instance(adverb(beautifully), [beautifully|Remaining], Remaining).
adverb_instance(adverb(delightfully), [delightfully|Remaining], Remaining).
adverb_instance(adverb(firmly), [firmly|Remaining], Remaining).
adverb_instance(adverb(lightly), [lightly|Remaining], Remaining).
adverb_instance(adverb(delicately), [delicately|Remaining], Remaining).
adverb_instance(adverb(wearily), [wearily|Remaining], Remaining).
adverb_instance(adverb(willfully), [willfully|Remaining], Remaining).
adverb_instance(adverb(quickly), [quickly|Remaining], Remaining).
adverb_instance(adverb(truthfully), [truthfully|Remaining], Remaining).
adverb_instance(adverb(randomly), [randomly|Remaining], Remaining).
adverb_instance(adverb(badly), [badly|Remaining], Remaining).
adverb_instance(adverb(slightly), [slightly|Remaining], Remaining).

verb_instance(verb(pushed), [pushed|Remaining], Remaining).
verb_instance(verb(gave), [gave|Remaining], Remaining).
verb_instance(verb(watched), [watched|Remaining], Remaining).
verb_instance(verb(forced), [forced|Remaining], Remaining).
verb_instance(verb(did), [did|Remaining], Remaining).
verb_instance(verb(took), [took|Remaining], Remaining).
verb_instance(verb(saw), [saw|Remaining], Remaining).
verb_instance(verb(stored), [stored|Remaining], Remaining).
verb_instance(verb(climbed), [climbed|Remaining], Remaining).
verb_instance(verb(admired), [admired|Remaining], Remaining).
verb_instance(verb(married), [married|Remaining], Remaining).
verb_instance(verb(appreciated), [appreciated|Remaining], Remaining).
verb_instance(verb(failed), [failed|Remaining], Remaining).
verb_instance(verb(left), [left|Remaining], Remaining).
verb_instance(verb(cheated), [cheated|Remaining], Remaining).


question(question(whom), [whom|Remaining], Remaining).
question(question(where), [where|Remaining], Remaining).
question(question(who), [who|Remaining], Remaining).
question(question(how), [how|Remaining], Remaining).
question(question(whose), [whose|Remaining], Remaining).
question(question(what), [what|Remaining], Remaining).
question(question(when), [when|Remaining], Remaining).
question(question(why), [why|Remaining], Remaining).
question(question(which), [which|Remaining], Remaining).

infinitive_verb_instance(verb(run), [run|Remaining], Remaining).
infinitive_verb_instance(verb(go), [go|Remaining], Remaining).
infinitive_verb_instance(verb(write), [write|Remaining], Remaining).
infinitive_verb_instance(verb(do), [do|Remaining], Remaining).
infinitive_verb_instance(verb(leave), [leave|Remaining], Remaining).
infinitive_verb_instance(verb(catch), [catch|Remaining], Remaining).
infinitive_verb_instance(verb(post), [post|Remaining], Remaining).
infinitive_verb_instance(verb(react), [react|Remaining], Remaining).

adjective_instance(adjective(large), [large|Remaining], Remaining).
adjective_instance(adjective(young), [young|Remaining], Remaining).
adjective_instance(adjective(dark), [dark|Remaining], Remaining).
adjective_instance(adjective(talented), [talented|Remaining], Remaining).
adjective_instance(adjective(dirty), [dirty|Remaining], Remaining).
adjective_instance(adjective(messier), [messier|Remaining], Remaining).
adjective_instance(adjective(brilliant), [brilliant|Remaining], Remaining).
adjective_instance(adjective(scariest ), [scariest |Remaining], Remaining).
adjective_instance(adjective(happy), [happy|Remaining], Remaining).
adjective_instance(adjective(cool), [cool|Remaining], Remaining).
adjective_instance(adjective(mischievous), [mischievous|Remaining], Remaining).
adjective_instance(adjective(garrulous), [garrulous|Remaining], Remaining).
adjective_instance(adjective(big), [big|Remaining], Remaining).
adjective_instance(adjective(empty), [empty|Remaining], Remaining).
adjective_instance(adjective(old), [old|Remaining], Remaining).
adjective_instance(adjective(good), [good|Remaining], Remaining).
adjective_instance(adjective(poor), [poor|Remaining], Remaining).
adjective_instance(adjective(bright), [bright|Remaining], Remaining).
adjective_instance(adjective(short), [short|Remaining], Remaining).
adjective_instance(adjective(white), [white|Remaining], Remaining).
adjective_instance(adjective(tall), [tall|Remaining], Remaining).

preposition_instance(preposit(over), [over|Remaining], Remaining).
preposition_instance(preposit(behind), [behind|Remaining], Remaining).
preposition_instance(preposit(under), [under|Remaining], Remaining).
preposition_instance(preposit(for), [for|Remaining], Remaining).
preposition_instance(preposit(off), [off|Remaining], Remaining).
preposition_instance(preposit(in), [in|Remaining], Remaining).
preposition_instance(preposit(upon), [upon|Remaining], Remaining).
preposition_instance(preposit(into), [into|Remaining], Remaining).
preposition_instance(preposit(after), [after|Remaining], Remaining).
preposition_instance(preposit(onto), [onto|Remaining], Remaining).
preposition_instance(preposit(within), [within|Remaining], Remaining).

conjunction_instance(conjunction(but), [but|Remaining], Remaining).
conjunction_instance(conjunction(or), [or|Remaining], Remaining).
conjunction_instance(conjunction(until), [until|Remaining], Remaining).
conjunction_instance(conjunction(although), [although|Remaining], Remaining).
conjunction_instance(conjunction(so), [so|Remaining], Remaining).
conjunction_instance(conjunction(because), [because|Remaining], Remaining).
conjunction_instance(conjunction(whether), [whether|Remaining], Remaining).
conjunction_instance(conjunction(yet), [yet|Remaining], Remaining).
conjunction_instance(conjunction(and), [and|Remaining], Remaining).

