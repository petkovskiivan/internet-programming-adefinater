# Hugo Award Books Database - Student Instructions

## Exam Overview
**Duration:** 2 hours  
**Total Points:** 100 (+ 25 bonus points available)  
**Passing Grade:** 60%  
**Tools Allowed:** All online resources, LLMs (ChatGPT, Claude, etc.), documentation, Stack Overflow

## What You're Building
Create a web application that displays and filters Hugo Award nominated and winning books from 1953-2025. Think of it as a searchable database interface for science fiction and fantasy literature.

## Files Provided
- `hugo-books-exam.json` - Your data source (24 books with edge cases)
- `hugo-books-exam-specification.md` - Detailed requirements  
- This instruction file

## Getting Started

### 1. Download the Files
- Save `hugo-books-exam.json` in your project folder
- This contains 24 carefully selected books with various edge cases

### 2. Basic Project Structure
Create these files:
```
your-project/
├── index.html
├── styles.css (optional - can embed in HTML)
├── script.js (optional - can embed in HTML)
└── hugo-books-exam.json
```

### 3. Minimum Requirements (60% Grade)
To pass, your application must:
- Display books in a table with all required columns
- Allow sorting by clicking column headers  
- Have a text filter for book titles
- Handle the provided data without crashing

## Strategy for Success

### Phase 1: Get the Basics Working (45 minutes)
1. **HTML Structure**
   - Create a table with proper headers
   - Add a text input for filtering
   - Include a loading message

2. **Load Data**
   - Fetch from `hugo-books-exam.json`
   - Display in table rows
   - Test that all 24 books appear

3. **Basic Filtering**
   - Connect text input to filter function
   - Filter by title (case-insensitive)

### Phase 2: Add Sorting (30 minutes)
1. **Click Handlers**
   - Add click events to table headers
   - Implement toggle ascending/descending

2. **Sort Functions**
   - Handle text columns (title, author, publisher)
   - Handle number columns (year)
   - Handle boolean columns (is_winner)

### Phase 3: Handle Edge Cases (30 minutes)
Focus on the test data edge cases:
1. **Series Display**
   - Books with `"series": false` should show "None"
   - Books with series names show the actual name

2. **Genres Display**
   - Empty arrays `[]` should show "None"  
   - Multiple genres should be comma-separated

3. **Special Characters**
   - Titles with quotes, apostrophes must display correctly
   - Long titles shouldn't break your layout

### Phase 4: Advanced Features (15 minutes)
Choose any advanced features to boost your grade:
- Performance optimization for large datasets
- Multi-column sorting
- Additional filters (winner/nominee, decade, etc.)
- Smart search with relevance ranking

## Important Test Cases
Your application will be tested with these specific books from the dataset:

**Edge Case Books:**
- `"The \"Impossible\" Book"` - Has quotes in title
- `"Empty Genre Book"` - Has empty genres array `[]`
- Books with `"series": false` - Should show "None"
- `"Book with 'Apostrophes' & Special-Characters..."` - Long title with special chars

**Normal Books:**
- `"Dune"` - Classic with series and multiple genres
- `"Neuromancer"` - Winner with series
- Various nominees and winners from different decades

## Tips for Using LLMs Effectively

### Good Prompts:
```
"Create a JavaScript function that sorts an array of book objects by title, 
handling case-insensitive sorting"

"How do I filter an array of objects in JavaScript where the title contains 
a search term, ignoring case?"

"Show me how to handle JSON data where some objects have series: false 
and display 'None' instead"
```

### What to Ask For:
- Specific functions for sorting and filtering
- HTML table structure examples
- CSS for responsive tables
- Error handling for fetch requests

### What NOT to Ask For:
- "Build the entire exam for me"
- Complete solutions without understanding

## Common Pitfalls to Avoid

1. **Showing "false" instead of "None"**
   ```javascript
   // Wrong:
   cell.textContent = book.series;
   
   // Right:
   cell.textContent = book.series === false ? "None" : book.series;
   ```

2. **Case-sensitive filtering**
   ```javascript
   // Wrong:
   books.filter(book => book.title.includes(searchTerm))
   
   // Right:
   books.filter(book => book.title.toLowerCase().includes(searchTerm.toLowerCase()))
   ```

3. **Not handling empty arrays**
   ```javascript
   // Wrong:
   cell.textContent = book.genres.join(", ");
   
   // Right:
   cell.textContent = book.genres.length > 0 ? book.genres.join(", ") : "None";
   ```

## Testing Your Solution

### Manual Testing Checklist:
- [ ] All 24 books display in table
- [ ] Click each column header to sort
- [ ] Try sorting both ascending and descending
- [ ] Search for "Dune" - should find the book
- [ ] Search for "impossible" - should find the edge case book
- [ ] Check that series shows "None" for books with `series: false`
- [ ] Check that empty genres show "None"
- [ ] Verify long titles don't break the layout

### Browser Console:
- Open Developer Tools (F12)
- Check for any red error messages
- Fix any JavaScript errors before submitting

## Submission Requirements

### File Format:
- **Single HTML file** (easiest) OR separate HTML/CSS/JS files
- Must work when opened locally in a browser
- No build process required (npm, webpack, etc.)

### What to Include:
- Working code that loads the provided JSON data
- Basic styling (doesn't need to be fancy)
- Comments explaining any complex logic
- All files needed to run your solution

### What NOT to Include:
- node_modules folders
- Build tools or configuration files
- External dependencies (except CDN links are OK)

## Grading Philosophy

**Remember:** This exam tests your ability to:
1. Work with real-world messy data
2. Handle edge cases gracefully  
3. Use online resources effectively
4. Write maintainable code

**60% (Pass):** Basic functionality works
**85% (Good):** Edge cases handled well
**100% (Excellent):** Advanced features implemented

## Time Management

| Time | Focus |
|------|-------|
| 0-15 min | Read requirements, set up files, plan approach |
| 15-60 min | Core functionality: table, data loading, basic filter |
| 60-90 min | Sorting implementation |
| 90-105 min | Edge case handling |
| 105-120 min | Advanced features, testing, cleanup |

## Final Advice

1. **Start Simple:** Get basic functionality working first
2. **Test Early:** Load data and display it before adding features
3. **Use Resources:** LLMs and documentation are your friends
4. **Focus on Requirements:** Don't over-engineer
5. **Handle Edge Cases:** They're worth significant points
6. **Comment Your Code:** Especially complex logic

Good luck! Remember, working code that handles the basic requirements well is much better than ambitious code that doesn't work.