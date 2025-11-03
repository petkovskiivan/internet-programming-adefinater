# Hugo Award Books Database Exam Specification

## Overview
Create a web application that displays and filters Hugo Award nominated and winning books from 1953 to 2025. Students will implement table display, sorting, filtering, and handle various data edge cases.

**Duration:** 2 hours  
**Tools Allowed:** All online resources, LLMs, documentation  
**Data Source:** `hugo-books-exam.json` (provided)

## Tier 1 Requirements (60 points - Basic Functionality)

### Core Display (25 points)
- Display books in a table with the following columns:
  - Title
  - Author
  - Year (Hugo award year)
  - Winner/Nominee status 
  - Publisher
  - Series (display "None" for books with `series: false`)
  - Genres (display as comma-separated list)

### Sorting (20 points)
- Single-column sorting (ascending/descending toggle)
- Must work correctly for:
  - Text fields (title, author, publisher)
  - Numeric fields (year)
  - Boolean-like fields (winner status)
  - Array fields (genres - sort by first genre)

### Filtering (10 points)
- Text filter for book title (case-insensitive contains match)
- Filter should work in real-time as user types

### Loading and Error States (5 points)
- Show loading indicator while data is being fetched
- Display appropriate error message if data fails to load

## Tier 2 Requirements (25 points - Edge Case Handling)

### Data Edge Cases (15 points)
- Handle books with `series: false` gracefully (display "None" or "—")
- Handle books with empty genres arrays (display "None" or "—")
- Handle books with multiple genres properly (display all genres)
- Handle very long book titles that might overflow table cells
- Handle special characters in titles, authors, and publishers (quotes, apostrophes, hyphens)

### Advanced Filtering (10 points)
- Handle filtering with no results (show "No books match your criteria")
- Ensure filter works correctly with the edge cases above
- Filter should be case-insensitive and handle partial matches

## Tier 3 Requirements (15 points - Advanced Features)
**Students must implement 2 of the following 4 options (choose any 2 for full credit):**

### Option 1: Performance Optimization (7.5 points)
- Implement virtual scrolling or pagination for large datasets (700+ books)
- Page must remain responsive with all books loaded
- Include comment explaining optimization strategy

### Option 2: Multi-Column Sorting (7.5 points)
- Allow sorting by multiple columns (Shift+click to add secondary sort)
- Visual indicators showing sort order and priority
- Proper handling of null/undefined values in sort

### Option 3: Advanced Filtering (7.5 points)
- Add dropdown filters for:
  - Winner/Nominee status
  - Decade (1950s, 1960s, 1970s, etc.)
  - Has Series (Yes/No filter for books with/without series)
- All filters should work together (AND logic)

### Option 4: Smart Search with Relevance (7.5 points)
- When text filter is active, sort results by relevance:
  - Exact title match first
  - Title starts with search term second
  - Title contains search term third
  - Author contains search term fourth
  - Any other field contains search term last
- Include relevance score indicator

## Bonus Tasks (25 points total - Optional)
**Each bonus task is worth 5 points:**

1. **Export Functionality**: Export filtered results to CSV format
2. **Genre Filter**: Multi-select dropdown for filtering by genres
3. **Year Range Filter**: Slider or dual input for filtering by year range  
4. **Author Filter**: Dropdown populated from unique authors in dataset
5. **Publisher Filter**: Dropdown populated from unique publishers in dataset

## Data Structure
Each book object contains:
```json
{
  "id": "12345",
  "title": "Book Title",
  "author": "Author Name", 
  "year": 2023,
  "is_winner": true,
  "publisher": "Publisher Name",
  "series": "Series Name" | false,
  "genres": ["Genre1", "Genre2"] | [],
  "url": "https://worldswithoutend.com/novel.asp?id=12345"
}
```

## Grading Rubric

### Tier 1 (60 points)
- **Table Display (25 points)**
  - All required columns: 15 points
  - Proper data formatting: 5 points
  - Responsive layout: 5 points

- **Sorting (20 points)**
  - Single column sort works: 12 points
  - Toggle ascending/descending: 5 points
  - Handles all data types: 3 points

- **Filtering (10 points)**
  - Text filter functional: 7 points
  - Real-time filtering: 3 points

- **Loading/Error States (5 points)**
  - Loading indicator: 3 points
  - Error handling: 2 points

### Tier 2 (25 points)
- **Edge Case Handling (15 points)**
  - Series false handling: 4 points
  - Empty genres handling: 3 points
  - Multiple genres display: 3 points
  - Long titles handling: 3 points
  - Special characters: 2 points

- **Advanced Filtering (10 points)**
  - No results state: 5 points
  - Case-insensitive matching: 3 points
  - Edge case compatibility: 2 points

### Tier 3 (15 points)
- Each chosen advanced feature: 7.5 points
- Partial credit for attempted but incomplete features

### Bonus (25 points)
- Each bonus feature: 5 points

## Deductions
- Console errors on page load: -5 points
- Application crashes on any interaction: -10 points
- Code doesn't run without modification: -15 points
- Missing basic HTML structure/CSS: -5 points

## Test Data Characteristics
The provided dataset contains approximately 700 Hugo-nominated books with these intentional edge cases:

- **Series Data**: ~40% have `series: false`, ~60% have actual series names
- **Genres**: ~5% have empty genre arrays, most have 2-4 genres
- **Special Characters**: Titles with quotes, apostrophes, colons, parentheses
- **Long Titles**: Some titles exceed 50 characters
- **Year Range**: Spans from 1953 to 2025
- **Winner Distribution**: ~20% winners, ~80% nominees
- **Publisher Variety**: Over 100 different publishers
- **Author Variety**: Over 400 unique authors

## Success Criteria
- **60% (Tier 1)**: Basic table with sorting and filtering - achievable with LLM help
- **85% (Tiers 1+2)**: Requires testing and understanding of edge cases
- **100% (All Tiers)**: Demonstrates advanced JavaScript skills and problem-solving

## Submission Requirements
- Single HTML file with embedded CSS/JavaScript OR separate files
- All files must work when opened locally in a browser
- No external build process required (CDN libraries allowed)
- Include brief comments explaining any complex logic
- Test with the provided dataset before submission

## Implementation Notes
- Use modern JavaScript (ES6+) features appropriately
- Ensure accessibility with proper ARIA labels
- Consider mobile responsiveness
- Focus on code readability and maintainability
- Performance matters - test with the full dataset

## Academic Integrity
- Use of LLMs and online resources is encouraged
- Understand and be able to explain any code you submit
- Test thoroughly with edge cases before submission
- Document any external libraries or resources used