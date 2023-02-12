<template>
    <div class="job">
        <div class="job-header">
            <img src="" alt="Logo">
            <a class="job-apply" href="">
                Solliciteer
            </a>
        </div>
        <div class="job-title">
            <h3>{{vacancy}}</h3>
        </div>
        <div class="job-tags">
            <p>
                {{location}} • {{type}} 
            </p>
        </div>
        <div class="job-additional-info">
            <h4>
                {{name}}
            </h4>
        </div>
    </div>
</template>

<script>
export default {
    name: "JobCard",
    props: {
        name: Text,
        vacancy: Text,
        location: Text,
        type: Text,
        logoUri: Text,
        postedTimestamp: Text,
    }
}
</script>

<style lang="scss" scoped>
    .job {
        box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
        padding: 20px;
        border-radius: 10px;
        .job-header {
            display: flex;
            justify-content: space-between;
            margin: 10px 0px;
            a.job-apply:link, a.job-apply:visited {
                border: 1.5px solid #eee;
                padding: 10px 12px;
                border-radius: 8px;
                background: #B47AEA;
                background: linear-gradient(to right, #B47AEA 23%, #FFC4EB 100%);
                -webkit-background-clip: text;
                -webkit-text-fill-color: transparent;
                font-weight: 600;
                text-decoration: none;
            }
        }
        .job-title {
            margin: 10px 0px;
            margin-top: 20px;
            h3 { 
                font-weight: 500;
            }
        }
        .job-tags {
            color: #6e6e6e;
            padding-bottom: 40px;
            border-bottom: 1.5px solid #eee;
        }
        .job-additional-info {
            margin-top: 15px;
            h4 {
                font-weight: 500;
            }
        }
    }
</style>