# Fact Extraction
We can use large language models like BERT and GPT to extract facts about entities.

## GPT-3

### Prompt

```txt
What facts do you know about Bob Dylan?

('Bob Dylan', 'BIRTH-DATE', '1941-5-24')
('Bob Dylan', 'BORN-IN', 'Minnesota')
('Bob Dylan',  'HAS-PROFESSION', 'songwriter')
('Bob Dylan',  'AWARDED', 'Nobel Prize')
('Bob Dylan',  'SIGNED-ARTEST', 'Albert Grossman')
('Bob Dylan', 'WROTE-SONG', 'The Times They Are A Changing')
('Bob Dylan', 'WROTE-SONG', 'Knockin' on Heaven's Door')
```

### Response

```txt
('Bob Dylan', 'WROTE-SONG', 'Blowin in the Wind')
('Bob Dylan', 'WROTE-SONG', 'Hurricane')
('Bob Dylan', 'WROTE-SONG', 'Subterranean Homesick Blues')
('Bob Dylan', 'WROTE-SONG', 'Masters of War')
('Bob Dylan', 'WROTE-SONG', 'Mr. Tambourine Man')
('Bob Dylan', 'WROTE-SONG', 'Like a Rolling Stone')
```