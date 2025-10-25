<template>
    <span>
        <div>Month</div>
        <select size="6">
            <option>j</option>
            <option>nov</option>
            <option>dec</option>
            <option>febr</option>
            <option>m</option>
            <option>sept</option>
        </select>
        <select size="6">
            <option>octo</option>
            <option>em</option>
            <option>uly</option>
            <option>a</option>
            <option>une</option>
            <option>an</option>
        </select>
        <select size="6">
            <option>ber</option>
            <option>y</option>
            <option>unary</option>
            <option>rch</option>
            <option>pril</option>
            <option>ugust</option>
        </select>
    </span>
    <div>
        <span>
            day
            <input type="number" value="0" />
        </span>
    </div>
    <div>
        <span>
            year
            <input type="text" value="1900" />
            <input type="range" min="1" max="100" value="50" />
        </span>
    </div>
</template>
