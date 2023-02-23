# Iterating-arrayBuffer
 
var ArrayBufferCursor = function() {
 var ArrayBufferCursor = function(arrayBuffer) {
 this.dataview = new DataView(arrayBuffer, 0);
 this.size = arrayBuffer.byteLength;
 this.index = 0;
 }
 ArrayBufferCursor.prototype.next = function(type) {
 switch(type) {
 case 'Uint8':
 var result = this.dataview.getUint8(this.index);
 this.index += 1;
 return result;
 case 'Int16':
 var result = this.dataview.getInt16(this.index, true);
 this.index += 2;
 return result;
 case 'Uint16':
 var result = this.dataview.getUint16(this.index, true);
