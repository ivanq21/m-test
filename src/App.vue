<template>
  <div id="app">
    <div class="container">
		<Title msg="Наши сервисы"/>
		<Cards :data="cardsData" />
		<div class="btns-wrapper">
			<div class="btn">
				<Button
					class="pink big"
					size="big"
					text="Оставить заявку"
					borderRadius="bottom"
				/>
			</div>
			<div class="btn">
				<Button
					class="light big"
					size="big"
					text="Узнать стоимость"
					borderRadius="top"
				/>
			</div>
		</div>
    </div>
  </div>
</template>

<script>
import Title from './components/Title.vue'
import Cards from './components/Cards.vue'
import servers from './assets/servers.svg';
import servers_icon from './assets/servers_icon.svg';
import objdb from './assets/database.svg';
import objdb_icon from './assets/hotbox.svg';
import graph from './assets/graph.svg';
import graph_icon from './assets/graph_icon.svg';
import cont from './assets/cont.svg';
import containers_icon from './assets/containers_icon.svg';
import big_data from './assets/big_data.svg';
import big_data_icon from './assets/big_data_icon.svg';
import auto_learn from './assets/auto_learn.svg';
import auto_learn_icon from './assets/auto_learn_icon.svg';
import cloud from './assets/cloud.svg';
import cloud_icon from './assets/cloud_icon.svg';
import logo from './assets/m_logo.svg';
import Button from './components/Button.vue';

const cardsData = [
    {
        id: 'servers',
        title: 'Виртуальные серверы',
        subtitle: 'IaaS-сервис для создания виртуальных машин без сложных настроек',
        bg_img: servers,
        icon: servers_icon,
        btn_text: 'Попробовать',
    },
    {
        id: 'obj_storage',
        title: 'Объектное хранилище',
        subtitle: 'S3-совместимое облачное хранилище для быстрой работы с большими объемами данных',
        bg_img: objdb,
        icon: objdb_icon,
        btn_text: 'Попробовать',
    },
    {
        id: 'graph_adapter',
        title: 'Графические адаптеры',
        subtitle: 'Мощные облачные вычисления на базе NVIDIA GPU без покупки собственных видеокарт',
        bg_img: graph,
        icon: graph_icon,
        btn_text: 'Попробовать',
    },
    {
        id: 'kubernetes',
        title: 'Контейнеры Kubernetes',
        subtitle: 'IaaS-сервис для создания виртуальных машин без сложных настроек',
        bg_img: cont,
        icon: containers_icon,
        btn_text: 'Попробовать',
    },
    {
        id: 'big_data',
        title: 'Большие данные',
        subtitle: 'IaaS-сервис для создания виртуальных машин без сложных настроек',
        bg_img: big_data,
        icon: big_data_icon,
        btn_text: 'Попробовать',
    },
    {
        id: 'cloud_db',
        title: 'Базы данных в облаке',
        subtitle: 'IaaS-сервис для создания виртуальных машин без сложных настроек',
        bg_img: cloud,
        icon: cloud_icon,
        btn_text: 'Попробовать',
    },
    {
        id: 'ai_learn',
        title: 'Машинное обучение',
        subtitle: 'IaaS-сервис для создания виртуальных машин без сложных настроек',
        bg_img: auto_learn,
        icon: auto_learn_icon,
        btn_text: 'Скоро запуск',
    },
    {
        id: 'mail_cloud',
        title: 'Cloud Solutions',
        subtitle: 'Скоро на платформе Cloud Solutions появятся новые сервисы',
        bg_img: '',
        icon: logo,
        btn_text: 'Быть в курсе',
    },
]

export default {
  name: 'App',
  components: {
    Title,
    Cards,
	Button,
  },
  data: () => {
    return {
      cardsData,
    }
  }
}
</script>

<style lang="scss">
	body {
		font-family: 'Roboto', sans-serif;
		margin: 0;
		background: #3420A3;
	}

	* {
		box-sizing: border-box;
	}

	#app {
	color: #fff;
	min-height: 100vh;
	}

	.container {
		width: 1100px;
		margin: 0 auto;
		padding: 60px 0;

		@media screen and (max-width: 1200px) {
			width: 100%;
			padding: 60px 5vw;
		}

		@media screen and (max-width: 768px) {
			padding: 60px 4vw;
		}
	}

	button {
		background: none;
		border: none;
	}

	.btns-wrapper {
		display: flex;
		justify-content: center;
		margin: 36px auto;

		button:first-child {
			margin-right: 20px;
		}

		@media screen and (max-width: 480px) {
			flex-direction: column;

			.btn {
				margin-bottom: 20px;
			}
		}
	}
</style>
