<template>
  <div id="home">
    <div class="left">
      <div class="logo">
        <p><img src="@/assets/_logo/the-godfather.svg" alt="Logo" /></p>
      </div>
      <nav>
        <ul>
          <li 
            v-for="(item, key) in employees" :key="key"
            @click="details">
            {{ item.name }}
          </li>
        </ul>
      </nav>
    </div>
    <div class="right">
      <!-- TODO component -->
      <div class="employee">
        <div class="img-employee">
          <p><img src="@/assets/_images/profile/Vito Corleone.jpg" alt="image" /></p>
        </div>
        <div class="wrapper-info">
          <h3 class="name-employee">
            {{ employees[0].name }}
          </h3>
          <div class="popularity">
            <p class="title">Popularity</p>
            <p class="ruler"></p>
          </div>
          <div class="content">
            <div class="colleagues">
              <span 
                v-for="(item, key) in employees[0].colleagues"
                :key="key"
                >
                {{ item }}
              </span>
            </div>
            {{ employees[0].biography }}
          </div>
        </div>
      </div>
      <!-- end component -->
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        employees: [
          {
            name: "Vito Corleone",
            popularity: 5,
            biography: "Vito Andolini's story starts in Corleone, Sicily. In 1901, the local mafia chieftain, Don Ciccio, murders Vito's father Antonio when he refuses to pay him tribute. Paolo, Vito's older brother, swears revenge, but Ciccio's men kill him too. Ciccio then sends his men to fetch nine-year old Vito. However, Vito's mother insists on going as well and begs Ciccio to spare Vito. Ciccio refuses, reasoning the boy will seek revenge as a grown man. Upon Ciccio's refusal, Vito's mother holds a knife to Ciccio's throat, allowing her son to escape while Ciccio's men kill her. Family friends smuggle Vito out of Sicily, putting him on a ship with immigrants traveling to America. Ellis Island immigration officials rename him Vito Corleone, using his village for his surname. He later uses Andolini as his middle name in acknowledgement of his family heritage.",
            image: "Vito Corleone.jpg",
            colleagues: ["Carlo Rizzi", "Luci Mancini"]
          },
          {
            name: "Carmelia Corleone",
            popularity: 2,
            biography: "Carmela was born in Sicily Italy in 1897, and emigrated to the United States shortly after the turn of the century. She married Vito Corleone in 1914; they were married for just over 40 years until Vito's death in 1955. They had four children – Sonny, Fredo, Michael and Connie. They also took in Sonny's friend Tom Hagen, who later served as the family consigliere. In the novel, Carmela Corleone is portrayed as a traditional Italian immigrant woman who speaks in very broken English. In the movies, however, she speaks fluent English as an adult, with a marked New York accent. In the novel, she develops a close relationship with Michael's girlfriend and future wife, Kay. She is given more expansive dialogue in The Godfather Part II, notably when she confronts her daughter Connie about her behavior early in the film, and when she discusses family life with Michael, who fears that his role as Don of the Corleone criminal empire will cost him his family. Carmela Corleone dies toward the end of the sequel.",
            image: "Carmelia Corleone.jpg",
            colleagues: []
          },
          {
            name: "Carlo Rizzi",
            popularity: 5,
            biography: "A half northern Italian, half Sicilian native of Nevada and former labourer, Rizzi migrated to New York City following trouble with the law and became a friend of Sonny Corleone, through whom he met Sonny's sister Connie in 1941 at a surprise birthday party for Sonny's father Vito. They were married on the last Saturday of August 1945 in a traditional Italian wedding at the Corleone mall, a compromise made in order to appease Vito, who was disappointed with his daughter's choice in a husband.",
            image: "Carlo Rizzi.jpg",
            colleagues: ["Vito Corleone", "Carmelia Corleone"]
          },
          {
            name: "Luci Mancini",
            popularity: 5,
            biography: "In the novel, Lucy is a fairly important supporting character, with several chapters dedicated to her story. After Sonny's death, Vito's consigliere, Tom Hagen sends Lucy to Las Vegas. She is given a small interest (five and later ten) in one of the family's hotels, primarily so that she can keep an eye on Vito's middle son, Fredo, who is learning the hotel and casino business. She also serves as a shareholder-of-record who has no criminal record: several such owners are necessary for a valid gaming license. On paper she is a millionaire, although she does not vote her shares in the casinos.",
            image: "Luci Mancini.jpg",
            colleagues: ["Carmelia Corleone"]
          }
        ],
      };
    },
    methods: {
      details() {
        // TODO
        // Click event emit data from parent component to child component
      }
    }
  };
</script>

<style lang="scss">
  #home {
    .left {
      position: fixed;
      width: 20%;
      background: rgba(0,0,0,0.5);
      height: 100%;
      top: 0;
      z-index: 4;
      .logo {
        width: 50%;
        margin: 0 auto;
        height: 30vh;
        display: flex;
        align-items: center;
      }
      nav {
        margin-top: 30px;
        ul {
          padding: 0;
          margin: 0;
          li {
            text-align: center;
            list-style: none;
            color: #3db5d7;
            font-size: 35px;
            padding: 5px 0;
            cursor: pointer;
            &:nth-child(2) {
              font-size: 18px;
            }
            &:nth-child(3) {
              color: #fff;
              font-size: 18px;
            }
            &:nth-child(4) {
              font-size: 22px;
            }
          }
        }
      }
    }
    .right {
      padding-left: 25%;
      background: #2e2e36;
      position: fixed;
      top: 30vh;
      left: 0;
      height: 100%;
      z-index: 3;
      .employee {
        display: flex;
        justify-content: flex-start;
        margin-top: -50px;
        .img-employee {
          width: 160px;
          margin-right: 50px;
          p {
            margin: 0;
            img {
              border-radius: 5px;
              border: 1px solid rgba(255,255,255,0.3);
              box-shadow: 0px 0px 30px 0px rgba(0,0,0,0.75);
            }
          }
        }
        .wrapper-info {
          width: calc(100% - 300px);
          text-align: left;
          .name-employee {
            color: #fff;
            font-size: 30px;
            margin: 0;
            margin-bottom: 35px;
          }
          .popularity {
            color: #fff;
            font-size: 16px;
            display: flex;
            align-items: center;
            .title {
              width: 10%;
            }
            .ruler {
              height: 5px;
              background: #1a1d24;
              width: 90%;
              position: relative;
              margin: 0;
              &:after {
                position: absolute;
                content: "";
                top: 50%;
                transform: translateY(-50%);
                left: 100px;
                background: #fff;
                width: 20px;
                height: 20px;
                border-radius: 50%;
                cursor: pointer;
              }
            }
          }
          .content {
            background: #1a1d24;
            padding: 30px;
            color: #fff;
            margin-top: 65px;
            line-height: 25px;
            .colleagues {
              font-size: 20px;
              font-weight: bold;
              margin-bottom: 10px;
              span {
                margin-right: 20px;
              }
            }
          }
        }
      }
    }
  }
</style>
