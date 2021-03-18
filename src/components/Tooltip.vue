<template>
  <div class="tooltip_i">
    <p class="star_border">i</p>
    <div class="tooltiptext_i">
			<div class="item">
				<div class="tooltip_title">Минимальная активность</div>
				<span
					>минимальная активность, сидячая работа, не требующая значительных
					физических нагрузок;</span
				>
			</div>
			<div class="item">
				<div class="tooltip_title">Умеренная активность</div>
				<span
					>слабый уровень активности: интенсивные упражнения не менее 20 минут
					один-три раза в неделю. Это может быть езда на велосипеде, бег
					трусцой, баскетбол, плавание, катание на коньках и т. д. Если вы не
					тренируетесь регулярно, но сохраняете занятый стиль жизни, который
					требует частой ходьбы в течение длительного времени, то выберите этот
					коэффициент;
				</span>
			</div>
			<div class="item">
				<div class="tooltip_title">Умеренная активность</div>
				<span
					>умеренный уровень активности: интенсивная тренировка не менее 30-60
					мин три-четыре раза в неделю (любой из перечисленных выше видов
					спорта);
				</span>
			</div>
			<div class="item">
				<div class="tooltip_title">Высокая активность</div>
				<span
					>тяжелая или трудоемкая активность: интенсивные упражнения и занятия
					спортом 5-7 дней в неделю. Трудоемкие занятия также подходят для этого
					уровня, они включают строительные работы (кирпичная кладка, столярное
					дело и т. д.), занятость в сельском хозяйстве и т. п.;
				</span>
			</div>
			<div class="item">
				<div class="tooltip_title">Экстремальная активность</div>
				<span
					>экстремальный уровень: включает чрезвычайно активные и/или очень
					энергозатратные виды деятельности: занятия спортом с почти ежедневным
					графиком и несколькими тренировками в течение дня; очень трудоемкая
					работа, например, сгребание угля или длительный рабочий день на
					сборочной линии. Зачастую этого уровня активности очень трудно
					достичь.</span
				>
			</div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.tooltip_i {
  position: relative;
  display: inline-block;
}

.tooltip_i .tooltiptext_i {
	column-count: 2;
  column-gap: 4%;
  visibility: hidden;
  position: absolute;
  min-width: 600px;
  background-color: #fff;
  color: #828181;
  text-align: left;
  padding: 5px 10px;
  bottom: 100%;
  right: 0;
  left: -172px;
  margin-bottom: 30px;
  min-height: 174px;
  font-family: Roboto;
  font-style: normal;
  font-weight: normal;
  font-size: 10px;
  line-height: 12px;
  z-index: 1;
  box-shadow: 0px 4px 14px rgba(0, 0, 0, 0.07);
	transition: all 0.55s;
}
.tooltiptext_i::after {
	content: "";
	position: absolute;
	border: 10px solid transparent;
	border-top: 10px solid #fff;
	border-right: 10px solid #fff;
	bottom: -20px;
	left: 161px;
}
.tooltip_i:hover .tooltiptext_i {
  visibility: visible;
}
.item {
  width: 100%;
}
.tooltip_title {
	padding: 7px 0;
  font-family: Roboto;
  font-style: normal;
  font-weight: bold;
  font-size: 15px;
  line-height: 18px;
  color: #00bc35;
}
</style>
