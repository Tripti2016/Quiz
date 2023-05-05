<template >
    <div class="reservation-box">
        <div>
            <div class="heading">
                <h3>{{ $props.completeData?.title }}</h3>
                <p>{{ $props.completeData?.disc }}</p>
            </div>
            <slot name="appbtn"></slot>
        </div>
        <div class="btn-box">
            {{ $props.completeData?.btns }}
        </div>
        <slot name="appbtn-2"></slot>

    </div>
</template>
<script>
export default {
    name: 'Reservation',
    props: {
        completeData: Object
    },
}
</script>
