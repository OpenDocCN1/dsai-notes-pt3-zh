

# TAC Knowledge Base Population (KBP) 2016

## Task 1: Cold Start KBP

The Cold Start KBP track builds a knowledge base from scratch using a given document collection and a predefined schema for the entities and relations that will comprise the KB. In addition to an end-to-end **KB Construction** task, Cold Start KBP includes a **Slot Filling (SF)** task to fill in values for predefined slots (attributes) for a given entity.

| Person | Organization |
|---|---|
| per:alternate_names | org:alternate_names |
| per:date_of_birth | org:political/religious_affiliation |
| per:age | org:top_members/employees |
| per:country_of_birth | org:number_of_employees/members |
| per:stateorprovince_of_birth | org:members |
| per:city_of_birth | org:member_of |
| per:origin | org:subsidiaries |
| per:date_of_death | org:parents |
| per:country_of_death | org:founded_by |
| per:stateorprovince_of_death | org:founded |
| per:city_of_death | org:dissolved |
| per:cause_of_death | org:country_of_headquarters |
| per:countries_of_residence | org:stateorprovince_of_headquarters |
| per:stateorprovinces_of_residence | org:city_of_headquarters |
| per:cities_of_residence | org:shareholders |
| per:schools_attended | org:website |

## Person and Organization

## Task 2: Entity Discovery and Linking (EDL)

The Entity Discovery and Linking (EDL) track aims to extract entity mentions from a source collection of textual documents in multiple languages (English, Chinese, and Spanish), and link them to an existing Knowledge Base (KB); an EDL system is also required to cluster mentions for those entities that don't have corresponding KB entries.

## Task 3: Event Track

The goal of the Event track is to extract information about events such that the information would be suitable as input to a knowledge base. The track includes **Event Nugget (EN)** tasks to detect and link events, and **Event Argument (EA)** tasks to extract event arguments and link arguments that belong to the same event.

## Task 4: Belief/Sentiment Track

The Belief and Sentiment track detects belief and sentiment of an entity toward another entity, relation, or event.

one topic in aclImdb: *Thriller and Suspense Films*

| JST positive | JST negative | reversed JST positive | reversed JST negative | MgS-LDA laudatory | MgS-LDA boring | MgS-LDA funny | MgS-LDA objective |
|---|---|---|---|---|---|---|---|
| good (0.035)<br>budget (0.031)<br>movie (0.026)<br>suspense (0.023)<br>plot (0.018) | dumb (0.035)<br>you (0.032)<br>tell (0.021)<br>plot (0.021)<br>predictable (0.019) | film (0.039)<br>story (0.035)<br>good (0.026)<br>some (0.018)<br>suspense (0.018) | movie (0.036)<br>dumb (0.034)<br>you (0.026)<br>club (0.023)<br>watch (0.019) | good (0.114)<br>great (0.036)<br>special (0.034)<br>first (0.026)<br>wonderful (0.019) | you (0.098)<br>watch (0.058)<br>dumb (0.039)<br>unfortunately (0.035)<br>acting (0.026) | laughing (0.067)<br>time (0.019)<br>story (0.018)<br>ridiculous (0.017)<br>funny (0.017) | people (0.154)<br>movie (0.064)<br>film (0.036)<br>characters (0.027)<br>scene (0.025) |

one topic in Customer Review Dataset: *Canon G3 Camera*

| JST positive | JST negative | reversed JST positive | reversed JST negative | MgS-LDA awesome | MgS-LDA annoyed | MgS-LDA expensive | MgS-LDA objective |
|---|---|---|---|---|---|---|---|
| camera (0.039)<br>you (0.037)<br>easy (0.033)<br>flash (0.028)<br>get (0.022) | camera (0.043)<br>time (0.023)<br>canon (0.023)<br>buy (0.022)<br>you (0.021) | camera (0.036)<br>you (0.028)<br>use (0.024)<br>digital (0.024)<br>canon (0.020) | camera (0.035)<br>you (0.031)<br>bad (0.027)<br>canon (0.027)<br>cost (0.021) | great (0.063)<br>good (0.050)<br>easy (0.042)<br>features (0.036)<br>other (0.024) | had (0.094)<br>bad (0.072)<br>more (0.046)<br>complaint (0.024)<br>bought (0.024) | purchased (0.085)<br>you (0.074)<br>expensive (0.066)<br>cannon (0.066)<br>price (0.023) | camera (0.207)<br>canon (0.072)<br>you (0.047)<br>digital (0.037)<br>online (0.037) |

