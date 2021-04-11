<template>
    <h1 class="mb-5 pb-3 border-bottom">
        File a Complaint
    </h1>
    <form class="row g-3">
        <div class="row my-2">
            <!-- <div class="col-md-6">
                <label for="email" class="form-label">Email</label>
                <input v-model.lazy.trim="userData.email" type="email" class="form-control" id="email" />
            </div> -->

            <!-- How V-Model works -->
            <div class="col-md-6">
                <label for="email" class="form-label">Email</label>
                <input 
                    :value="userData.email"
                    @input="userData.email = $event.target.value"
                    type="email" 
                    class="form-control" 
                    id="email" 
                />
            </div>
            <div class="col-md-6">
                <label for="password" class="form-label">Password</label>
                <input v-model.lazy.trim="userData.password" type="password" class="form-control" id="password" />
            </div>
        </div>
        <div class="row my-2">
            <div class="col-12">
                <label for="age" class="form-label">Age</label>
                <input v-model.number.lazy.trim="userData.age" type="number" class="form-control" id="age" />
            </div>
        </div>

        <div class="row my-2">
            <div class="mb-3">
                <label for="Message" class="form-label">Message</label>
                <textarea v-model="message" class="form-control" id="Message" rows="3"></textarea>
            </div>
        </div>

        <div class="row my-2">
            <div class="col-sm-6 col-lg-3">
                <div class="form-check">
                    <input v-model="sendMail" value="sendNormalMail" class="form-check-input" type="checkbox" id="sendNormalMail" />
                    <label class="form-check-label" for="sendNormalMail">
                        Send Mail
                    </label>
                </div>
            </div>
            <div class="col-sm-6 col-lg-3">
                <div class="form-check">
                    <input v-model="sendMail" value="sendInfoMail" class="form-check-input" type="checkbox" id="sendInfoMail" />
                    <label class="form-check-label" for="sendInfoMail">
                        Send InfoMail
                    </label>
                </div>
            </div>
        </div>

        <div class="row my-2">
            <div class="col-sm-6 col-lg-3">
                <div class="form-check">
                    <input class="form-check-input" v-model="gender" value="Male" type="radio" name="Gender" id="Male" />
                    <label class="form-check-label" for="Male">
                        Male
                    </label>
                </div>
            </div>

            <div class="col-sm-6 col-lg-3">
                <div class="form-check">
                    <input class="form-check-input" v-model="gender" value="Female" type="radio" name="Gender" id="Female" />
                    <label class="form-check-label" for="Female">
                        Female
                    </label>
                </div>
            </div>
        </div>

        <div class="row my-2">
            <div class="col-md-12">
                <label for="Proiority" class="form-label">Proiority</label>
                <select id="Proiority" class="form-select" v-model="proioritySelected">
                    <!-- <option selected disabled>Choose...</option> -->
                    <option 
                        v-for="(priority, index) in proiorityOptions"
                        :disabled="index === 0" :key="index">
                        {{ priority.text }}
                    </option>
                </select>
            </div>
        </div>

        <div class="row mt-4 pb-5 border-bottom">
            <div class="col-12">
                <button type="submit" class="btn btn-primary">Submit</button>
            </div>
        </div>
    </form>

    <div class="row my-5">
        <div class="col-lg-12">
            <div class="card text-white bg-dark">
                <h5 class="card-header">Your Data</h5>
                <div class="card-body">
                    <p class="card-text">Mail: {{ userData.email }}</p>
                    <p class="card-text">Password: {{ userData.password }}</p>
                    <p class="card-text">Age: {{ userData.age }}</p>
                    <p style="white-space: pre" class="card-text">Message: {{ message }}</p>

                    <p class="card-text">Send Mail:  
                        <!-- {{ sendMail }} -->
                        <ul v-if="sendMail.length > 0">
                            <li v-for="(item, index) in sendMail" :key="index">{{ item }}</li>
                        </ul>
                    </p>

                    <p class="card-text">Gender: {{ gender }}</p>
                    <p class="card-text">Proiority: {{ proioritySelected }}</p>

                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Form",
    data() {
        return {
            userData: {
                email: '',
                password: '',
                age: null
            },
            message: `A Default New Message
            
            another line here
            `,
            sendMail: [],
            gender: null,
            proioritySelected: 'Please select an option',
            proiorityOptions: [
                {value: null, text: 'Please select an option'},
                {value: 'b', text: 'High'}, 
                {value: 'c', text: 'Medium'}, 
                {value: 'd', text: 'Low'}
            ]
        };
    },
};
</script>
