# CTC Score

## Installation
```
pip install -e .
```

## Example
```python
from ctc_score import DialogScorer

dialog_history = "so, i'm reading the latest film from studio ghibli is out the tale of princess kaguya. dunno if you're familiar with them, but studio ghibli has made a lot of great animated films, like spirited away, and princess mononoke \n i don't think i have heard of them. i have heard that one of the directors recently passed away, and his last film was nominated for an academy award \n yeah, sadly, disney ( which owns the american rights to the films ) doesn't tend to promote them very much. i think they're worried they 'll cut into their \" home grown \" market. anyway, dunno if you even like animated movies, but they're worth checking out. \n i don't watch them very often. apparently there was a showing of the recent film in a park in d.c. that's one u.s. city i haven't been to \n sadly, i haven't been to dc either, although i've always wanted to visit there. apparently there's a lot of interesting going down this summer. they're having a crab feast at the navy - marine corps stadium. they 'll have 100 gallons of crab soup! can you imagine that much soup? \n\n"
hypo = "i recently met a girl who lives in that area, and she said the nightlife is worth visiting for. it sounds like many of the events feature jazz music. do you listen to jazz very often?"
fact = "from left, emma baker, daniel saperstein and taylor mulitz of flasher will perform this summer's final fort reno concert. ( jared soares for the washington post ) monday, july 30 25th birthday celebration at national postal museum : celebrate 25 years of this institution devoted to the long history of the u.s. postal service with daytime festivities that include cupcakes, birthday postcards, a photo booth and a special scavenger hunt with prizes. 11 a.m. to 2 p.m. free. tuesday, july 31 \" the color purple \" at kennedy center : the tony award - winning musical revival, based on the pulitzer prize - winning alice walker novel of the same name, features jazz, ragtime, gospel and blues with a story about an african american woman named celie surviving poverty in the south during the 1930s. through aug. 26. $ 69-$149. ask a harry potter scholar at southeast neighborhood library : come to this talk from tolanda henderson, a librarian from george washington university, who has used the j.k. rowling book series as a text in academia. commune with other muggles who prove that it's not just kids and young adults who obsess about the boy who lived. 7 p.m. free. wednesday, aug. 1 rico nasty at the fillmore silver spring : two summers ago, rico nasty was a teenage loudmouth from the maryland suburbs, generating buzz on youtube for spitting surly, rainbow - tinted rhymes. now, after signing a deal with atlantic records, the 21-year - old singer is on her way to becoming one of the brightest voices in rap music.\n"

scorer = DialogScorer(dataset='topical_chat', aligner='E')

scorer.score(fact=fact, dialog_history=dialog_history, hypo=hypo, aspect='engagingness')
```