// src/tests/unit/MyComponent.test.js
import React from 'react';
import { render, fireEvent } from '@testing-library/react';
import MyComponent from '../MyComponent';

describe('MyComponent', () => {
  it('renders correctly', () => {
    const { getByText } = render(<MyComponent />);
    expect(getByText('Hello World')).toBeInTheDocument();
  });

  it('handles button click', () => {
    const { getByText } = render(<MyComponent />);
    const button = getByText('Click me');
    fireEvent.click(button);
    expect(getByText('Button clicked')).toBeInTheDocument();
  });
});
// server/tests/unit/myFunction.test.js
const myFunction = require('../myFunction');

describe('myFunction', () => {
  it('returns the correct result', () => {
    const result = myFunction(2, 3);
    expect(result).toBe(5);
  });

  it('handles errors correctly', () => {
    expect(() => myFunction('a', 3)).toThrowError('Invalid input');
  });
  // server/tests/integration/api.test.js
const request = require('supertest');
const app = require('../app');

describe('GET /api/data', () => {
  it('returns the correct data', async () => {
    const response = await request(app).get('/api/data');
    expect(response.status).toBe(200);
    expect(response.body).toEqual({ data: 'Hello World' });
  });

  it('handles errors correctly', async () => {
    // simulate an error
    jest.spyOn(app, 'get').mockImplementationOnce(() => {
      throw new Error('Mocked error');
    });
    const response = await request(app).get('/api/data');
    expect(response.status).toBe(500);
  });
});
// cypress/integration/my-spec.js
describe('My App', () => {
  it('visits the app root url', () => {
    cy.visit('/');
    cy.contains('h1', 'My App');
  });

  it('navigates to the about page', () => {
    cy.visit('/');
    cy.get('[data-test="about-link"]').click();
    cy.url().should('include', '/about');
  });
});
});
