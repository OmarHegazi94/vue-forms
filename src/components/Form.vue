<template>
    <h1 class="mb-5 pb-3 border-bottom">
        File a Complaint
    </h1>
    <form class="row g-3">
        <div class="row my-2">
            <div class="col-md-6">
                <label for="email" class="form-label">Email</label>
                <input type="email" class="form-control" id="email" />
            </div>
            <div class="col-md-6">
                <label for="password" class="form-label">Password</label>
                <input type="password" class="form-control" id="password" />
            </div>
        </div>
        <div class="row my-2">
            <div class="col-12">
                <label for="age" class="form-label">Age</label>
                <input type="text" class="form-control" id="age" />
            </div>
        </div>

        <div class="row my-2">
            <div class="mb-3">
                <label for="Message" class="form-label">Message</label>
                <textarea class="form-control" id="Message" rows="3"></textarea>
            </div>
        </div>

        <div class="row my-2">
            <div class="col-md-12">
                <label for="Proiority" class="form-label">Proiority</label>
                <select id="Proiority" class="form-select">
                    <option selected>Choose...</option>
                    <option>...</option>
                </select>
            </div>
        </div>

        <div class="row my-2">
            <div class="col-sm-6 col-lg-3">
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" id="sendMail" />
                    <label class="form-check-label" for="sendMail">
                        Send Mail
                    </label>
                </div>
            </div>
            <div class="col-sm-6 col-lg-3">
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" id="sendInfoMail" />
                    <label class="form-check-label" for="sendInfoMail">
                        Send InfoMail
                    </label>
                </div>
            </div>
        </div>

        <div class="row my-2">
            <div class="col-sm-6 col-lg-3">
                <div class="form-check">
                    <input class="form-check-input" type="radio" name="Gender" id="Male" />
                    <label class="form-check-label" for="Male">
                        Male
                    </label>
                </div>
            </div>

            <div class="col-sm-6 col-lg-3">
                <div class="form-check">
                    <input class="form-check-input" type="radio" name="Gender" id="Female" checked />
                    <label class="form-check-label" for="Female">
                        Female
                    </label>
                </div>
            </div>
        </div>

        <div class="row mt-4 pb-3 border-bottom">
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
                    <p class="card-text">Mail: </p>
                    <p class="card-text">Password: </p>
                    <p class="card-text">Age: </p>
                    <p class="card-text">Message: </p>

                    <p class="card-text">Send Mail: 
                        <ul>
                            <li></li>
                        </ul>
                    </p>

                    <p class="card-text">Gender: </p>
                    <p class="card-text">Proiority: </p>

                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Form",
    data() {
        return {};
    },
};
</script>
