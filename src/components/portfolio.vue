<template>
  <div id="portfolio">
    <div class="row">
      <div class="col-xl-4" v-for="(item, index) in items" :key="index">
        <!-- Button trigger modal -->
        <div class="seeMore" data-toggle="modal" :data-target="'#exampleModal' + index">
          <img :src="item.thumbnail" />
          <div class="bg">
            <img src="../assets/icons/see.png" />
          </div>
        </div>
        <!-- Modal -->
        <div class="modal fade" :id="'exampleModal' + index" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
          <div class="modal-dialog modal-dialog-centered modal-xl">
            <div class="modal-content">
              <div class="modal-header">
                <h5 class="modal-title" id="exampleModalLabel">{{item.category}}</h5>
                <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                  <span aria-hidden="true">✕</span>
                </button>
              </div>
              <div class="modal-body">
                <div class="row">
                  <div class="col-xl-6 space">
                    <h4>{{item.title}}</h4>
                    <h5>{{item.body}}</h5>
                    <h5>Responsibility : {{item.responsibility}}</h5>
                  </div>
                  <div class="col-xl-6">
                    <div class="video-responsive" v-if="item.type == 'clip'">
                        <iframe :src="item.work" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                    </div>  
                    <img :src="item.work" v-if="item.type == 'image'" />  
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import aboutMe from '../assets/image/aboutMe.jpg'
import website from '../assets/image/thumbnail/web.jpg'
import motion from '../assets/image/thumbnail/motion.jpg'
import documentary from '../assets/image/thumbnail/documentary.jpg'
import graphic from '../assets/image/thumbnail/graphic.jpg'

export default {
  name: 'portfolio',
  data(){
    return{
      items:[
        {
          thumbnail: website,
          category: 'Web Application',
          title: 'Web Application Tracking Progress System of Undergraduate Student Project for Department of Computer and Information Technology',
          body: 'Recording evidence from work between teachers and students.',
          responsibility: 'Frontend, Coordinator',
          work: 'https://www.youtube.com/embed/ZZx1TQKO5ok',
          type: 'clip'
        },
        {
          thumbnail: website,
          category: 'Web Application',
          title: 'Paithiaokan',
          body: 'A collection of tourist attractions in Thailand divided into mountains, waterfalls, and beaches.',
          responsibility: 'Frontend, UXUI',
          work: 'https://www.youtube.com/embed/2MYJ-7mOrfw',
          type: 'clip'
        },
        // {
        //   thumbnail: img1,
        //   category: 'Prototype Web',
        //   title: 'Lorem2',
        //   body: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsum beatae delectus maiores magni quis animi aliquam sint commodi quibusdam sit? Distinctio reprehenderit non a recusandae itaque nesciunt sed qui labore!',
        // responsibility: 'Frontend, UXUI',
        //   work: 'Prototype Web',
        //   type: 'text'
        // },
        {
          thumbnail: motion,
          category: 'Motion Graphic',
          title: 'EMMALINE Hotel',
          body: 'Motion graphics about the content of cloud computing.',
          responsibility: 'Motion Graphic, Script',
          work: 'https://www.youtube.com/embed/22yc-I6_1rY',
          type: 'clip'
        },
        {
          thumbnail: documentary,
          category: 'Documentary',
          title: 'Tie-Dye Cloth',
          body: 'The short documentary describes the charm and beauty of tie-dye fabrics.',
          responsibility: 'Script, Coordinator',
          work: 'https://www.youtube.com/embed/qToYbQp_NWc',
          type: 'clip'
        },
        {
          thumbnail: graphic,
          category: 'Graphic Design',
          title: 'About Me Project Camp 1',
          body: 'University educational guidance for high school students',
          responsibility: 'Graphic',
          work: aboutMe,
          type: 'image'
        }
      ]
    }
  }
}
</script>