<template>
    <div>
        <Container :variant="variant" >
            <Icon :variant="variant" >
                <!--<Cup />-->
            </Icon>
            <Content>
                <Title> {{ title }} </Title>
                <span> {{ text }} </span>
            </Content>
                <Dismiss>ok!</Dismiss>
            <!--{
                dismiss &&
                <Dismiss>ok!</Dismiss>
            }-->
        </Container>
    </div>
</template>

<script>
import styled from 'vue-styled-components';
//import Cup from '../assets/Cup'

export const Container = styled.div`
    display:flex;
    justify-content: center;
    align-items: center;
    padding: 15px;
    position: absolute;

    ${({variant}) => {
        if (variant == 'rounded') {
            return (`
                background-color: #550527;
                border-radius: 75px;
                margin: auto;
                left: 0;
                right: 0;
                width: fit-content;
            `)
        } else if (variant == 'dismiss') {
            return (`
                width: fill-available;
                background-color: #d74251;
                border-radius: 10px;
            `)
        } else {
            return (`
                width: fill-available;
                background-color: #7b70ab;
            `)
        }
    }}
`
export const Icon = styled.div`
    margin-right: 25px;

    ${({variant}) => {
        if (variant == 'rounded') {
            return (`
                background-color: white;
                border-radius: 100%;
                min-width: 85px;
                min-height: 85px;
                display: flex;
                align-items: center;
                justify-content: center;
            `)
        }
    }}
`
export const Content = styled.div`
    display:flex;
    flex-direction: column;
    align-items: baseline;
    text-align: left;
    color: white;
`

export const Title = styled.span`
    font-weight: bold;
`
export const Dismiss = styled.div`
    color: white;
    display: flex;
    text-transform: uppercase;
    margin-left: 25px;
    padding-left: 25px;
    height: 50px;
    align-items: center;
    border-left: 1px solid white;
    font-weight: bold;
`

export default {
  name: 'LvlUp',
  data() {
        return {

        };
    },
    components: {
        Container,
        Icon,
        //Cup,
        Content,
        Title,
        Dismiss,

    },
    props: {
        title: String, 
        text: String, 
        dismiss: Boolean,
        variant: {
            type: String,
            default: 'line'
        }
    },
}
</script>

<style scoped>



</style>
