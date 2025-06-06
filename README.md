# 🚗 TrueCar Market Scraper

[![Python](https://img.shields.io/badge/python-v3.8+-blue.svg?style=for-the-badge)](https://www.python.org/downloads/)
[![BeautifulSoup](https://img.shields.io/badge/beautifulsoup4-4.13.3-green.svg?style=for-the-badge)](https://pypi.org/project/beautifulsoup4/)
[![Pandas](https://img.shields.io/badge/pandas-2.2.3-orange.svg?style=for-the-badge)](https://pandas.pydata.org/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=for-the-badge)](LICENSE)

## Project Structure (For the Organized People)

```
toyota-market-scraper/
├── cars.ipynb                       # The main event (actual code)
├── requirements.txt                 # Dependencies (the usual suspects)
├── cars-toyota-tacoma-4runner.csv   # Your data (CSV edition)
├── cars-toyota-tacoma-4runner.xlsx  # Your data (Excel edition)
└── README.md                        # You are here
```

## The Origin Story (aka "Mom Needs Help")

So here's the thing — my mom had this school assignment about web scraping Toyota listings, and naturally, she asked me for help. Plot twist: I'd never scraped anything in my life. Not even a dinner plate.

But you know how it is... you can't just tell your mom "sorry, I don't know how to do that." So I did what any reasonable person would do: I dove headfirst into the beautiful chaos of BeautifulSoup documentation at 8 PM (I'm an oldhead and get sleepy around 9 PM so God bless me), armed with nothing but determination and way too much tea.

The assignment? Pretty straightforward actually — scrape some car data and export it to CSV/Excel. Done. Assignment complete. Mom happy.

But here's where things got interesting... I couldn't just leave it there. Once I had the basic scraper working, I started thinking: "What if I could make this actually useful?" And thus began my journey down the rabbit hole of feature creep (in the best possible way).

## What This Thing Actually Does

This scraper hits up TrueCar and grabs data on Toyota Tacomas and 4Runners around Boston. It's like having a really dedicated friend who refreshes car listings obsessively, except this friend:

- Actually knows regex (unlike me when I started)
- Doesn't get tired after page 3
- Can clean data without complaining
- Won't judge your questionable car choices

**The data it collects:**
- Vehicle names (with all the trim level nonsense)
- Mileage (because apparently that matters)
- Prices (the fun part)
- Years, makes, models (the boring but necessary parts)

## The Tech Stack (aka "Things I Googled")

- **Python** — because apparently it's good at this stuff
- **BeautifulSoup** — sounds like a Campbell's product, scrapes like a dream
- **Requests** — for when you need to politely ask websites for their data
- **Pandas** — not the animal (I checked)
- **Regex** — the dark arts of pattern matching

## Getting Started (If You're Brave Enough)

### Step 1: Prerequisites
```bash
pip install -r requirements.txt
```
*Note: This assumes you have Python installed. If not... well, that's a whole other adventure.*

### Step 2: Run the Thing
```bash
# Start Jupyter Notebook
jupyter notebook

# Then open cars.ipynb in your browser
# Run cells one by one and watch the magic happen
# (or debug when it inevitably doesn't work on the first try)
```

*Note: This is a Jupyter notebook (.ipynb), not a regular Python script. You can't just `python cars.py` it — trust me, I tried.*

**Alternative if you want a script:**
```bash
# Convert notebook to Python script
jupyter nbconvert --to script cars.ipynb

# Then run the generated script
python cars.py
```

### Step 3: Marvel at Your Data
Your scraped data will appear as:
- `cars-toyota-tacoma-4runner.csv` — for the spreadsheet people
- `cars-toyota-tacoma-4runner.xlsx` — for the Excel enthusiasts

## What You Get (Sample Data)

| Mileage | Price  | Year | Make   | Model   |
|---------|--------|------|--------|---------|
| 35,990  | $31,998| 2022 | Toyota | Tacoma  |
| 50,398  | $35,998| 2022 | Toyota | 4Runner |

*309 rows of this goodness, because apparently Boston has a lot of Toyotas*

## The Journey (Technical Stuff Hidden in Story Form)

### Problem #1: "What Even Is HTML?"
First challenge was figuring out how websites work. Turns out they're just text files with angle brackets everywhere. Who knew?

**Solution:** BeautifulSoup makes it almost readable. Almost.

### Problem #2: "Why Is Nothing Where I Think It Should Be?"
Spent an embarrassing amount of time trying to find price data that was hiding in `<span>` tags with random class names.

**Solution:** Developer tools became my best friend. Chrome's "inspect element" is basically cheat codes for web scraping.

### Problem #3: "The Data Looks Like Garbage"
Raw scraped data included gems like:
- "35,990 miles" (contains both numbers and words)
- "$31,998" (dollar signs are apparently characters)
- "Used 2022 ToyotaTacoma SR Double Cab..." (everything smooshed together)

**Solution:** Regex patterns that would make a computer science professor weep (tears of joy or horror, unclear).

## The Cleaning Pipeline (aka "Making Sense of Chaos")

```
Messy HTML → BeautifulSoup Magic → Data Extraction → Regex Wizardry → Clean Data → Victory Dance
```

Each step involved approximately 47 Stack Overflow searches and at least one "why isn't this working" moment.

## Beyond the Assignment (Where Things Got Fun)

The school assignment ended at "export to CSV/Excel." Mission accomplished, mom happy, grade secured. But I couldn't stop there — turns out building stuff is addictive.

### Current Expansion Plans
- [ ] **Tableau Dashboard** — because pretty charts make everything better
- [ ] **Power BI Reports** — diversifying my Microsoft skills  
- [ ] **Python Plots** — time to make matplotlib bend to my will

### Future Features (The "Why Not?" Phase)
- [ ] **Scheduled Scraping** — set it and forget it (until it breaks)
- [ ] **Price Alerts** — "your dream Tacoma just dropped $2k!"
- [ ] **Trend Analysis** — finally answer "is this a good deal?"
- [ ] **More Car Sites** — CarMax, AutoTrader, that sketchy Craigslist guy
- [ ] **Predictive Models** — AI-powered car shopping (probably)

### The Debug Chronicles (Coming Soon)
Planning to document the whole debugging journey with photos and explanations, including:
- Screenshots of my most spectacular failures
- The Claude conversations where I had to say "no, simpler please"
- How AI assistance can be amazing but also... overly ambitious
- Finding the balance between "helpful AI suggestions" and "wait, what was the actual problem again?"

Because let's be honest — the debugging process is where the real learning happens, and it's way messier (and more interesting) than the final clean code suggests.

## Things I Learned (The Hard Way)

1. **Websites don't like being scraped** — hence the user agent spoofing
2. **Data is always messier than you think** — always budget time for cleaning
3. **Regex is both powerful and terrifying** — use responsibly
4. **Error handling is your friend** — because websites change without warning
5. **Documentation is actually helpful** — who would've thought?
6. **AI assistants are great but enthusiastic** — Claude suggested 47 different approaches when I just needed to fix one regex pattern
7. **Sometimes the simplest solution is the right one** — even when the AI wants to rebuild everything from scratch
8. **Debugging is actually the fun part** — once you get past the initial panic

## The Real Talk Section

**What went well:** Built a functional scraper without prior experience. Completed the assignment (CSV/Excel export), then kept going because why stop there? Data comes out clean and analysis-ready. Mom got an A.

**What could be better:** Error handling could be more robust. The regex patterns make me slightly uncomfortable. Sometimes I overcomplicate things (thanks, Claude, for the 15 different ways to parse a single string).

**The Claude Factor:** Having an AI coding buddy was amazing for bouncing ideas around, but also... Claude really likes suggesting complex solutions. Half my debugging involved saying "no, let's try the simple thing first" and then realizing the simple thing actually worked.

**Would I do it again?** Absolutely. Next time I'll probably start with the simple approach instead of immediately jumping to the "enterprise-grade solution" that Claude keeps suggesting.

**The Assignment vs. Reality:** School assignment = basic scraper + CSV export. My version = that plus everything else I could think of. This is either called "going above and beyond" or "feature creep," depending on your perspective.

## Contributing (If You Want To Join This Chaos)

Got ideas? Want to fix my questionable code choices? Pull requests welcome!

Some ways to help:
- Add support for other car models (because why stop at Toyota?)
- Improve the data cleaning (my regex skills have room for growth)
- Build visualizations (I promise to learn Tableau properly)
- Add tests (I know, I know, I should've done this first)

## Legal Stuff (The Boring But Important Part)

This scraper:
- Respects rate limits (mostly)
- Uses public data only
- Doesn't break any terms of service (that I know of)
- Is for educational purposes (and car shopping)

---

*Started as homework help, evolved into a legitimate project. Funny how that works.*

**The Bottom Line:** Sometimes the best way to learn something is to just jump in and figure it out as you go. This project is proof that you don't need to be an expert to build something useful — you just need to be stubborn enough to keep Googling until it works.

Got questions? Found bugs? Want to share your own "learned it for mom" stories? Hit me up.
