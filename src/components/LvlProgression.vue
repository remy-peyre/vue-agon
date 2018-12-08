<template>
  <div>
    <LineContainer>
        <PhotoContainer>
            <NoPicture>photo</NoPicture>
            <!--A faire -->
            <!--<Picture src={photo} />-->
        </PhotoContainer>
        <ProgressBarContainer :variant="variant" >
            <ProgressBar :variant="variant" >
                <Progress :variant="variant" :progress="current/total * 100" >
                    <!-- {{toDisplay}} -->
                </Progress>
            </ProgressBar>
        </ProgressBarContainer>
    </LineContainer>
    <GeometryContainer :rounded="variant.startsWith('rounded')" :progress="current/total * 100" >
        <GeometryContent>
            <!--{{toDisplay}}-->
        </GeometryContent>
    </GeometryContainer>
  </div>
</template>

<script>
import styled from 'vue-styled-components';

const LineContainer = styled.div`
  display: flex;
  align-items: center;
`;
const PhotoContainer = styled.div`
  background-color: darkcyan;
  height: 100px;
  width: 100px;
  border-radius: 100%;
  border: 1px solid black;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1;
`;
const NoPicture = styled.div`
  height: 70px;
  width: 70px;
  border-radius: 100%;
  border: 1px solid black;
  background-color: black;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 14px;
`;
const Picture = styled.img`
  height: 70px;
  width: 70px;
  border-radius: 100%;
  object-fit: cover;
`;
const ProgressBarContainer = styled('div', {variant: String })`
  height: 50px;
  width: 250px;
  background-color: ${({variant}) => variant === 'line-outline' ? 'transparent' : 'darkcyan' };
  border-radius: 10px;
  border: 1px solid black;
  margin-left: -20px;
  display: flex;
  align-items: center;
  padding: 0px 15px;
`;
const ProgressBar = styled('div', {variant: String })`
  width: inherit;
  height: 20px;
  background-color: ${({variant}) => variant === 'line-outline' ? 'transparent' : 'darkcyan' };
  border-radius: 3px;
  border: 1px solid black;
`;
const Progress = styled('div', { progress: Number, variant: String })`
  height: 20px;
  line-height: 20px;
  ${({variant, progress}) => variant == 'line-outline'
      ? (`
          background-image: linear-gradient(left, darkcyan, darkcyan ${progress}%, transparent ${progress}%, transparent 100%);
          background-image: -webkit-linear-gradient(left, darkcyan, darkcyan ${progress}%, transparent ${progress}%, transparent 100%);
      `)
      : (`
          background-image: linear-gradient(left, white, white ${progress}%, transparent ${progress}%, transparent 100%);
          background-image: -webkit-linear-gradient(left, white, white ${progress}%, transparent ${progress}%, transparent 100%);
      `)
  }
`;
const GeometryContainer = styled('div', { progress: Number, variant: String })`
  position: relative;
  display: inline-block;
  margin: 1rem;
  width: 120px;
  height: 120px;
  background-color: #ddd;

  &:before {
      content: '';
      position: absolute;
      top: 15px;
      left: 15px;
      width: 90px;
      height: 90px;
      background-color: white;
  }
  &:after {
      content: '';
      display: inline-block;
      width: 100%;
      height: 100%;
      background-color: #63B8FF;
      ${({progress}) => {
          return progress < 50
          ? (`
              background-image: linear-gradient(90deg, #ddd 50%, transparent 50%, transparent), linear-gradient(${90 + 3.6 * progress}deg, #63B8FF 50%, #ddd 50%, #ddd);
          `)
          : (`
              background-image: linear-gradient(${-90 + 3.6 * (progress - 50)}deg, #63B8FF 50%, transparent 50%, transparent), linear-gradient(270deg, #63B8FF 50%, #ddd 50%, #ddd);
          `)
      }}
  }
  ${({rounded}) => rounded
      ? (`
          border-radius: 50%;
          &:before {border-radius: 50%;}
          &:after {border-radius: 50%;}
      `)
      : (`
          border-radius: 10px;
          &:after {border-radius: 10px;}
      `)
  }
`;
const GeometryContent = styled.div`
  letter-spacing: -2px;
  position: absolute;
  top: 50%;
  width: 100%;
  line-height: 1;
  margin-top: -0.75rem;
  text-align: center;
  font-size: 1.5rem;
  color: #777;
`;


export default {
    name: 'LvlProgression',
    data() {
        return {
            // toDisplay: '',
            /*variant: 'line',
            photo: '',
            total: 100,
            current: 1,
            percent: false,*/
        };
    },
    components: {
        LineContainer,
        PhotoContainer,
        NoPicture,
        Picture,
        ProgressBarContainer,
        ProgressBar,
        Progress,
        GeometryContainer,
        GeometryContent,
    },
    props: {
        photo: String, 
        total: Number, 
        progress: Number, 
        current: Number,
        percent: Boolean,
        variant: {
            type: String,
            default: 'line'
        }
    },
}
</script>

<style scoped>

</style>
