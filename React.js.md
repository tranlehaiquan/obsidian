### React hook "use"
https://react.dev/reference/react/use
Using to read Context or Promise value.

Use to read promise value example.
```tsx
const delay = (ms: number) => new Promise(resolve => setTimeout(resolve, ms));
const userPromise = fetchUser();
async function fetchUser() {
	console.log('Starting fetch...');
	await delay(1000);
	console.log('Fetch complete!');
	return { name: 'victor' };
}

const TestSuspense: React.FC<Props> = () => {
	console.log('Rendering TestSuspense... 1');
	const data = use(userPromise);
	console.log('Rendering TestSuspense... 2');
	return (
		<div>
			TestSuspense {JSON.stringify(data)}
		</div>
	);
}
	
function App() {
	return (
		<React.Suspense fallback="loading...">
			<TestSuspense />
		</React.Suspense>
	);
}
```
