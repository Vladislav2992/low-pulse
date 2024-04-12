<template>
    <div class="operation">
                <div class="operation__top">
                    <span class="gray"></span>
                    <h3>Operational</h3>
                </div>
                <div class="operation__body">
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span class="red"></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
            </div>
</template>

<style lang="scss" scoped>
.operation {
    position: absolute;
    width: 568px;
    bottom: 35px;
    right: 114px;
}
span {
    display: block;
    width: 6px;
    height: 20px;
    border-radius: 4px;
    background-color: rgba(54, 213, 108, .6);
}
h3 {
    font-weight: 600;
    font-size: 13px;
}
.operation__top {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    color: rgba(54, 213, 108, .6);
    margin-bottom: 10px;
}
.gray {
    background-color: #738199;
    width: 117px;
    height: 11px;
    border-radius: 4px;
}
.red {
    background: #DF484A;
}
.operation__body {
    display: flex;
    gap: 3px;
    justify-content: space-between;
}
@media (max-width: 1060px) {
    .operation {
        display: none;
    }
}
</style>