<script>
    let name = '';
    let email = '';
    let subject = '';
    let message = '';

    function handleSubmit(event) {
        event.preventDefault();
        // Handle form submission (e.g., send data to a server)
        console.log('Form submitted:', {name, email, subject, message});
        // Reset form after submission if needed
        name = '';
        email = '';
        subject = '';
        message = '';
    }
</script>

<div class="two-column-layout">
    <div class="left-column">
        <form on:submit={handleSubmit} class="max-w-lg mx-auto p-4 bg-white shadow-md rounded">
            <div class="mb-4">
                <label class="block text-gray-700 text-sm font-bold mb-2" for="name">
                    Enter Your Name
                </label>
                <input
                        type="text"
                        id="name"
                        bind:value={name}
                        required
                        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        placeholder="Name"
                />
            </div>

            <div class="mb-4">
                <label class="block text-gray-700 text-sm font-bold mb-2" for="email">
                    Enter Your Email
                </label>
                <input
                        type="email"
                        id="email"
                        bind:value={email}
                        required
                        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        placeholder="Email"
                />
            </div>

            <div class="mb-4">
                <label class="block text-gray-700 text-sm font-bold mb-2" for="subject">
                    Enter Your Subject
                </label>
                <input
                        type="text"
                        id="subject"
                        bind:value={subject}
                        required
                        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        placeholder="Subject"
                />
            </div>

            <div class="mb-4">
                <label class="block text-gray-700 text-sm font-bold mb-2" for="message">
                    Enter Your Message Here
                </label>
                <textarea
                        id="message"
                        bind:value={message}
                        required
                        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        rows="4"
                        placeholder="Message"
                ></textarea>
            </div>

            <div class="flex items-center justify-between">
                <button
                        type="submit"
                        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
                >
                    Submit
                </button>
            </div>
        </form>
    </div>

    <div class="left-column">

    </div>
</div>