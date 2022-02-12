<script>
	import Button from '$lib/Button.svelte';

	export let companyPhone = '000-000-0000';
	export let companyEmail = 'example@email.com';

	let companyAnchorPhone = companyPhone.split('-').join();
	let name = '';
	let email = '';
	let message = '';
	let disabled = false;
	let messageStatus = 'not sent';

	const sendMessage = async (event) => {
		event.preventDefault();
		if (name === '' || email === '' || message === '') {
			return (messageStatus = 'blank forms');
		}
		disabled = true;
		messageStatus = 'sending';
		const data = { name, email, message };
		const options = {
			method: 'POST',
			headers: { 'Content-Type': 'application/json' },
			body: JSON.stringify(data)
		};
		fetch('/index.json', options)
			.then((res) => res.json())
			.then((res) => {
				res.message === 'success' ? (messageStatus = 'sent') : (messageStatus = 'error');
			})
			.catch((err) => (messageStatus = 'error'));
	};
</script>

<div class="flex flex-col justify-start items-center w-full">
	<div>
		<ul class="flex flex-col justify-center items-start w-full mb-8">
			<li class="flex items-center w-full h-full mb-4">
				<svg
					class="w-6 h-6"
					fill="currentColor"
					viewBox="0 0 20 20"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						d="M2 3a1 1 0 011-1h2.153a1 1 0 01.986.836l.74 4.435a1 1 0 01-.54 1.06l-1.548.773a11.037 11.037 0 006.105 6.105l.774-1.548a1 1 0 011.059-.54l4.435.74a1 1 0 01.836.986V17a1 1 0 01-1 1h-2C7.82 18 2 12.18 2 5V3z"
					/>
				</svg>
				<a class="ml-2 text-xl cursor-text" href="tel:+1{companyAnchorPhone}"> {companyPhone} </a>
			</li>

			<li class="flex items-center w-full h-full">
				<svg
					class="w-6 h-6"
					fill="currentColor"
					viewBox="0 0 20 20"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z" /><path
						d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"
					/>
				</svg>
				<a class="ml-2 text-xl" href="mailto:{companyEmail}" target="_blank" rel="noreferrer">
					{companyEmail}
				</a>
			</li>
		</ul>
	</div>
	<form id="contact-form" class="flex flex-col justify-center items-center w-80 bg-white shadow">
		<fieldset class="grid grid-cols-1 gap-y-8 w-full p-12 text-left">
			<div>
				<label for="name" class="text-lg pb-1">
					Name<span class="text-red-500 font-bold"> *</span>
				</label>
				<input
					name="name"
					id="name"
					class="w-full p-1 m-0 text-black text-base font-sans font-semibold border-2 border-gray-200 bg-white"
					bind:value={name}
					{disabled}
					type="text"
					maxLength="100"
					required={true}
				/>
			</div>

			<div>
				<label for="email" class="text-lg pb-1 text-left">
					Email
					<span class="text-red-500 font-bold"> *</span>
				</label>
				<input
					name="email"
					id="email"
					class="w-full p-1 m-0 text-black text-base font-sans font-semibold border-2 border-gray-200 bg-white"
					bind:value={email}
					{disabled}
					type="email"
					maxLength="100"
					required={true}
				/>
			</div>

			<div>
				<label for="message" class="text-lg pb-1 text-left">
					Message
					<span class="text-red-500 font-bold"> *</span>
				</label>
				<textarea
					name="message"
					id="message"
					class="w-full p-1 m-0 text-black text-base font-sans font-semibold border-2 border-gray-200 bg-white"
					bind:value={message}
					{disabled}
					type="text"
					maxLength="500"
					required={true}
				/>
			</div>

			<div class="flex flex-col items-center">
				{#if messageStatus === 'not sent'}
					<Button onClick={sendMessage} {disabled}>SEND MESSAGE</Button>
				{:else if messageStatus === 'sending'}
					<p class="bg-blue-300 p-4 font-semibold shadow">sending...</p>
				{:else if messageStatus === 'sent'}
					<p class="bg-green-400 p-4 font-semibold shadow">Message Sent!</p>
				{:else if messageStatus === 'failed to send'}
					<p class="bg-red-300 p-4 font-semibold shadow">Message failed to send. Try again later</p>
				{:else if messageStatus === 'blank forms'}
					<p class="bg-red-300 p-4 mb-6 font-semibold shadow">Please fill out all forms</p>
					<Button onClick={sendMessage} {disabled}>SEND MESSAGE</Button>
				{/if}
			</div>
		</fieldset>
	</form>
</div>
