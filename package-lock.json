const express = require('express');
const app = express();

app.use(express.json());

// 1. About info
const about = {
  name: 'Medha',
  major: 'Computer Science',
  year: '2029',
  hometown: 'Kansas City'
};

// 2. Projects / experiences
let projects = [
  {
    title: 'USC Neuro Imaging Lab Research',
    description: 'Worked remotely on research involving EEG and imaging data analysis, including cleaning, processing, and visualizing data.',
    tech: ['R', 'Data Analysis', 'Visualization']
  },
  {
    title: 'Personal Tutoring Service',
    description: 'Created customized lesson plans for students in competitive math and test prep based on their goals and learning styles.',
    tech: ['Teaching', 'Curriculum Design', 'Communication']
  },
  {
    title: 'Startland Social Change Internship',
    description: 'Helped plan and support a social impact initiative focused on access, financial literacy, and community problem-solving.',
    tech: ['Research', 'Planning', 'Communication']
  }
];

// 3. Creative endpoint
const favorites = {
  favoriteSport: 'Tennis',
  favoriteSubject: 'Math',
  favoriteInterest: 'Data analysis',
  favoriteFocus: 'Problem solving'
};

// GET /api/about
app.get('/api/about', (req, res) => {
  res.json(about);
});

// GET /api/projects
app.get('/api/projects', (req, res) => {
  res.json(projects);
});

// POST /api/projects
app.post('/api/projects', (req, res) => {
  const { title, description, tech } = req.body;

  if (!title || !description || !tech) {
    return res.status(400).json({
      error: 'title, description, and tech are required'
    });
  }

  if (!Array.isArray(tech)) {
    return res.status(400).json({
      error: 'tech must be an array'
    });
  }

  const newProject = {
    title,
    description,
    tech
  };

  projects.push(newProject);
  res.status(201).json(newProject);
});

// Creative endpoint
app.get('/api/favorites', (req, res) => {
  res.json(favorites);
});

// Home route
app.get('/', (req, res) => {
  res.send('Medha Mini Portfolio API is running!');
});

// Start server
const PORT = 3000;
app.listen(PORT, () => {
  console.log(`Server listening on http://localhost:${PORT}`);
});