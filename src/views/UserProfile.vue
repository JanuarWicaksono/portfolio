<template>
    <div>
        <base-header class="header pb-8 pt-5 pt-lg-8 d-flex align-items-center"
            style="min-height: 600px; background-image: url(img/theme/profile.jpeg); background-size: cover; background-position: center top;">
            <!-- Mask -->
            <span class="mask bg-gradient-danger opacity-6"></span>
            <!-- Header container -->
            <div class="container-fluid d-flex align-items-center">
                <div class="row">
                    <div class="col-lg-7 col-md-10">
                        <h1 class="display-2 text-white">Hey Whats Up! This is Januar Wicaksono from Indonesia</h1>
                        <p class="text-white mt-0 mb-5">Fullstack Developer</p>
                        <!-- <a href="#!" class="btn btn-info">Edit profile</a> -->
                    </div>
                </div>
            </div>
        </base-header>

        <div class="container-fluid mt--7">
            <div class="row">

                <div class="col-xl-4 order-xl-4 mb-2 mb-xl-4">
                    <div class="card card-profile shadow">
                        <div class="row justify-content-center">
                            <div class="col-lg-3 order-lg-2">
                                <div class="card-profile-image">
                                    <a href="#">
                                        <img src="img/theme/profile1x1.jpeg" class="rounded-circle">
                                    </a>
                                </div>
                            </div>
                        </div>
                        <div class="card-header text-center border-0 pt-8 pt-md-4 pb-0 pb-md-4">
                            <div class="d-flex justify-content-between">
                                <base-button size="sm" type="info" class="mr-4">Connect</base-button>
                                <base-button size="sm" type="default" class="float-right">Message</base-button>
                            </div>
                        </div>
                        <div class="card-body pt-0 pt-md-4">
                            <div class="row">
                                <div class="col">
                                    <div class="card-profile-stats d-flex justify-content-center mt-md-5">
                                        <div>
                                            <span class="heading">22</span>
                                            <span class="description">Friends</span>
                                        </div>
                                        <div>
                                            <span class="heading">10</span>
                                            <span class="description">Photos</span>
                                        </div>
                                        <div>
                                            <span class="heading">89</span>
                                            <span class="description">Comments</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="text-center">
                                <h3>
                                    Januar Wicaksono<span class="font-weight-light">, 25</span>
                                </h3>
                                <div class="h5 font-weight-300">
                                    <i class="ni location_pin mr-2"></i>Jakarta, Indonesia
                                </div>
                                <div class="h5 mt-4">
                                    <i class="ni business_briefcase-24 mr-2"></i>Fullstack Developer
                                </div>
                                <div>
                                    <i class="ni education_hat mr-2"></i>Islamic University Of Indonesia
                                </div>
                                <hr class="my-4" />
                                <p>Laravel - Lumen - Codeigniter - Vuejs</p>
                                <a href="#">Show more</a>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="col-xl-8 order-xl-8 mb-2 mb-xl-8">
                    <div class="card shadow" :class="type === 'dark' ? 'bg-default': ''">
                        <div class="card-header border-0" :class="type === 'dark' ? 'bg-transparent': ''">
                            <div class="row align-items-center">
                                <div class="col">
                                    <h3 class="mb-0" :class="type === 'dark' ? 'text-white': ''">
                                        Project
                                    </h3>
                                </div>
                                <!-- <div class="col text-right">
                                    <base-button type="primary" size="sm">See all</base-button>
                                </div> -->
                            </div>
                        </div>

                        <div class="table-responsive">
                            <base-table class="table align-items-center table-flush"
                                :class="type === 'dark' ? 'table-dark': ''"
                                :thead-classes="type === 'dark' ? 'thead-dark': 'thead-light'" tbody-classes="list"
                                :data="tableData">
                                <template slot="columns">
                                    <th>Project</th>
                                    <th>Budget</th>
                                    <th>Status</th>
                                    <th>Users</th>
                                    <th>Completion</th>
                                    <th></th>
                                </template>

                                <template slot-scope="{row}">
                                    <th scope="row">
                                        <div class="media align-items-center">
                                            <a href="#" class="avatar rounded-circle mr-3">
                                                <img alt="Image placeholder" :src="row.img">
                                            </a>
                                            <div class="media-body">
                                                <span class="name mb-0 text-sm">{{row.title}}</span>
                                            </div>
                                        </div>
                                    </th>
                                    <td class="budget">
                                        {{row.budget}}
                                    </td>
                                    <td>
                                        <badge class="badge-dot mr-4" :type="row.statusType">
                                            <i :class="`bg-${row.statusType}`"></i>
                                            <span class="status">{{row.status}}</span>
                                        </badge>
                                    </td>
                                    <td>
                                        <div class="avatar-group">
                                            <a href="#" class="avatar avatar-sm rounded-circle" data-toggle="tooltip"
                                                data-original-title="Ryan Tompson">
                                                <img alt="Image placeholder" src="img/theme/team-1-800x800.jpg">
                                            </a>
                                            <a href="#" class="avatar avatar-sm rounded-circle" data-toggle="tooltip"
                                                data-original-title="Romina Hadid">
                                                <img alt="Image placeholder" src="img/theme/team-2-800x800.jpg">
                                            </a>
                                            <a href="#" class="avatar avatar-sm rounded-circle" data-toggle="tooltip"
                                                data-original-title="Alexander Smith">
                                                <img alt="Image placeholder" src="img/theme/team-3-800x800.jpg">
                                            </a>
                                            <a href="#" class="avatar avatar-sm rounded-circle" data-toggle="tooltip"
                                                data-original-title="Jessica Doe">
                                                <img alt="Image placeholder" src="img/theme/team-4-800x800.jpg">
                                            </a>
                                        </div>
                                    </td>

                                    <td>
                                        <div class="d-flex align-items-center">
                                            <span class="completion mr-2">{{row.completion}}%</span>
                                            <div>
                                                <base-progress :type="row.statusType" :show-percentage="false"
                                                    class="pt-0" :value="row.completion" />
                                            </div>
                                        </div>
                                    </td>

                                    <td class="text-right">
                                        <base-dropdown class="dropdown" position="right">
                                            <a slot="title" class="btn btn-sm btn-icon-only text-light" role="button"
                                                data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                                                <i class="fas fa-ellipsis-v"></i>
                                            </a>

                                            <template>
                                                <a class="dropdown-item" href="#">Action</a>
                                                <a class="dropdown-item" href="#">Another action</a>
                                                <a class="dropdown-item" href="#">Something else here</a>
                                            </template>
                                        </base-dropdown>
                                    </td>

                                </template>

                            </base-table>
                        </div>

                        <!-- <div class="card-footer d-flex justify-content-end"
                            :class="type === 'dark' ? 'bg-transparent': ''">
                            <base-pagination total="30"></base-pagination>
                        </div> -->

                    </div>
                </div>

            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'user-profile',
        data() {
            return {
                model: {
                    username: '',
                    email: '',
                    firstName: '',
                    lastName: '',
                    address: '',
                    city: '',
                    country: '',
                    zipCode: '',
                    about: '',
                },
                tableData: [{
                        img: 'img/theme/bootstrap.jpg',
                        title: 'Argon Design System',
                        budget: '$2500 USD',
                        status: 'pending',
                        statusType: 'warning',
                        completion: 60
                    },
                    {
                        img: 'img/theme/angular.jpg',
                        title: 'Angular Now UI Kit PRO',
                        budget: '$1800 USD',
                        status: 'completed',
                        statusType: 'success',
                        completion: 100
                    },
                    {
                        img: 'img/theme/sketch.jpg',
                        title: 'Black Dashboard',
                        budget: '$3150 USD',
                        status: 'delayed',
                        statusType: 'danger',
                        completion: 72
                    },
                    {
                        img: 'img/theme/react.jpg',
                        title: 'React Material Dashboard',
                        budget: '$4400 USD',
                        status: 'on schedule',
                        statusType: 'info',
                        completion: 90
                    },
                    {
                        img: 'img/theme/vue.jpg',
                        title: 'Vue Paper UI Kit PRO',
                        budget: '$2200 USD',
                        status: 'completed',
                        statusType: 'success',
                        completion: 100
                    }
                ]
            }
        },
    };
</script>
<style></style>