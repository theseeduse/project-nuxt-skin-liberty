<template>
    <div class="Liberty">
        <div id="top"></div>
        <div class="nav-wrapper">
            <nav class="navbar navbar-dark">
                <nuxt-link class="navbar-brand" to="/">더시드위키</nuxt-link>
                <ul class="nav navbar-nav">
                    <li class="nav-item">
                        <nuxt-link class="nav-link" to="/RecentChanges"><span class="fa fa-refresh"></span><span class="hide-title">최근 변경</span></nuxt-link>
                    </li>
                    <li class="nav-item">
                        <nuxt-link class="nav-link" to="/RecentDiscuss"><span class="fa fa-comments"></span><span class="hide-title">최근 토론</span></nuxt-link>
                    </li>
                    <li class="nav-item">
                        <nuxt-link class="nav-link" to="/random"><span class="fa fa-random"></span><span class="hide-title">임의 문서</span></nuxt-link>
                    </li>
                    <li class="nav-item">
                        <dropdown>
                            <template #toggle>
                                <a class="nav-link dropdown-toggle dropdown-toggle-fix" href="#" @click.prevent>
                                    <span class="fa fa-gear"></span><span class="hide-title">도구</span>
                                </a>
                            </template>
                            <div class="dropdown-menu" role="menu">
                                <nuxt-link to="/NeededPages" class="dropdown-item">작성이 필요한 문서</nuxt-link>
                                <nuxt-link to="/OrphanedPages" class="dropdown-item">고립된 문서</nuxt-link>
                                <nuxt-link to="/UncategorizedPages" class="dropdown-item">분류가 되지 않은 문서</nuxt-link>
                                <nuxt-link to="/OldPages" class="dropdown-item">편집된 지 오래된 문서</nuxt-link>
                                <nuxt-link to="/ShortestPages" class="dropdown-item">내용이 짧은 문서</nuxt-link>
                                <nuxt-link to="/LongestPages" class="dropdown-item">내용이 긴 문서</nuxt-link>
                                <nuxt-link to="/BlockHistory" class="dropdown-item">차단 내역</nuxt-link>
                                <nuxt-link to="/RandomPage" class="dropdown-item">RandomPage</nuxt-link>
                                <nuxt-link to="/Upload" class="dropdown-item">파일 올리기</nuxt-link>
                                <nuxt-link to="/License" class="dropdown-item">라이선스</nuxt-link>
                                <template v-if="false">
                                    <div class="dropdown-divider"></div>
                                    <nuxt-link class="dropdown-item">null</nuxt-link> 
                                </template>
                            </div>
                        </dropdown>
                    </li>
                </ul>
                <div class="navbar-login">
                    <dropdown class="login-menu">
                        <template #toggle>
                            <a id="login-menu" class="dropdown-toggle" type="button">
                                <img v-if="false" class="profile-img">
                                <span v-else class="fa fa-user"></span>
                            </a>
                        </template>
                        <div class="dropdown-menu dropdown-menu-right login-dropdown-menu">
                            <div v-if="false" class="username dropdown-item">
                                <b>d</b><br>Member
                            </div>
                            <div v-else-if="true" class="username dropdown-item">
                                <b>ip</b><br>Please login!
                            </div>
                            <div class="dropdown-divider"></div>
                            <a href="#" class="dropdown-item">설정</a>
                            <div class="dropdown-divider"></div>
                        </div>
                    </dropdown>
                </div>
            </nav>
        </div>
        <div class="content-wrapper">
            <div class="liberty-sidebar">
                <div class="liberty-right-fixed">
                    <div class="live-recent">
                        <div class="live-recent-header">
                            <ul class="nav nav-tabs">
                                <li class="nav-item">
                                    <a id="liberty-recent-tab1" class="nav-link active">최근 변경</a>
                                </li>
                            </ul>
                        </div>
                        <!--recent-card-->
                        <div class="live-recent-footer">
                            <nuxt-link to="/RecentChanges" title="최근 변경내역"><span class="label label-info">더 보기</span></nuxt-link>
                        </div>
                    </div>
                </div>
            </div>
            <div class="container-fluid liberty-content">
                <div v-if="true" id="site-notice" class="notification">
                    <span class="label" v-html="공지" />
                </div>
                <div class="liberty-content-header">
                    <div class="title">제목</div>
                </div>
            </div>
            <div class="liberty-content-main wiki-article">
                <nuxt />
                <div v-if="false">
                    <h2>Liberty skin license</h2>
                    <pre>{{ License }}</pre>
                </div>
                <div class="clearfix"></div>
            </div>
            <div id="bottom" class="liberty-footer">
                    <ul class="footer-places" v-html="푸터" />
                    <ul class="footer-icons">
                        <li class="footer-poweredbyico">
                            <a href="//gitlab.com/librewiki/Liberty-MW-Skin">Liberty</a> | <a href="//theseed.io/">the seed</a>
                        </li>
                    </ul>
            </div>
        </div>
    </div>
</template>

<style>
@import "./css/bootstrap.min.css";
@import "./css/font-awesome.min.css";
@import "./css/font/Noto Sans KR.css";
@import "./css/default.css";
@import './css/default_mobile.css';
@import "./css/dark.css";
</style>

<script>
import Dropdown from './components/dropdown';
import License from "raw-loader!./LICENSE";

export default {
    components: {
        Dropdown
    },
    data() {
        return {
            License
        }
    }
}
</script>