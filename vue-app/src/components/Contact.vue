<template>
    <div class="contact-container">
        <h1>Contact Us!</h1>
        <form action="Contact.vue" method="POST">
            <div class="input-container">
                <label for="name">Name:</label>
                <input type="text" name="name" placeholder="Full Name..." required>
                <label for="phone">Phone:</label>
                <input type="text" name="phone" placeholder="Phone Number..." required>
                <label for="email">Email:</label>
                <input type="email" name="email" placeholder="Email Address..." required>
                <button class="submit" type="submit" name="submit" value="Send">Submit</button>
            </div>
        </form>
    </div>
</template>

<script>

export default {
    name: 'Contact-comp',
}

</script>

<style scoped>
    h1 {
        text-align: center;
    }
    .contact-container {
        height: 690px;
    }

    form {
        position: relative;
        top: 125px;
        border: black solid 1px;
        width: 60%;
        margin: 0 auto;
        padding: 1em;
    }
    .input-container {
        display: flex;
        flex-direction: column;
        max-width: 500px;
        margin: 0 auto;
        text-align: left;
    }

    input {
        margin: 1em;
    }

    label {
        margin-left: 1em;
    }

    .submit {
        background: rgb(1, 240, 1);
        color: white;
        font-family: 'Poppins';
        font-weight: 600;
        border-radius: 10px;
        border: solid .5px black;
        padding: .7em 1em;
        width: 100px;
        cursor: pointer;
    }
</style>