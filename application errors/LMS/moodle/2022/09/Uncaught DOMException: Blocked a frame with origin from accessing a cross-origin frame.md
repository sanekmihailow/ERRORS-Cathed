<d>
  <details>
    <summary> Links </summary>
    
[moodle.org/forum](https://moodle.org/mod/forum/discuss.php?d=417929)
    
</details>
</d>

```js
yui_combo.php?rollup/3.17.2/yui-moodlesimple-min.js:10 

Uncaught DOMException: Blocked a frame with origin "https://example.com" from accessing a cross-origin frame.

    at E.getValue (https://example.com/theme/yui_combo.php?rollup/3.17.2/yui-moodlesimple-min.js:10:4851)
    at c.DEFAULT_GETTER (https://example.com/theme/yui_combo.php?rollup/3.17.2/yui-moodlesimple-min.js:98:2185)
    at c._get (https://example.com/theme/yui_combo.php?rollup/3.17.2/yui-moodlesimple-min.js:98:2812)
    at c.get (https://example.com/theme/yui_combo.php?rollup/3.17.2/yui-moodlesimple-min.js:98:2614)
    at o._uploadComplete (https://example.com/theme/yui_combo.php?3.17.2/intl/intl-min.js&3.17.2/event-simulate/event-simulate-min.js&3.17.2/async-queue/async-queue-min.js&3.17.2/gesture-simulate/gesture-simulate-min.js&3.17.2/node-event-simulate/node-event-simulate-min.js&3.17.2/json-stringify/json-stringify-min.js&3.17.2/io-upload-iframe/io-upload-iframe-min.js&3.17.2/io-form/io-form-min.js&2in3/2.9.0/build/yui2-treeview/yui2-treeview-min.js&3.17.2/cookie/cookie-min.js&3.17.2/array-extras/array-extras-min.js&3.17.2/array-invoke/array-invoke-min.js&3.17.2/arraylist/arraylist-min.js&3.17.2/model/model-min.js&3.17.2/model-list/model-list-min.js&3.17.2/datatable-core/datatable-core-min.js&3.17.2/view/view-min.js&3.17.2/datatable-head/datatable-head-min.js&3.17.2/datatable-body/datatable-body-min.js&3.17.2/datatable-table/datatable-table-min.js&3.17.2/datatable-base/datatable-base-min.js&3.17.2/datatable-column-widths/datatable-column-widths-min.js&3.17.2/datatable-message/lang/datatable-message_en.js:58:1697)
    at c.<anonymous> (https://example.com/theme/yui_combo.php?3.17.2/intl/intl-min.js&3.17.2/event-simulate/event-simulate-min.js&3.17.2/async-queue/async-queue-min.js&3.17.2/gesture-simulate/gesture-simulate-min.js&3.17.2/node-event-simulate/node-event-simulate-min.js&3.17.2/json-stringify/json-stringify-min.js&3.17.2/io-upload-iframe/io-upload-iframe-min.js&3.17.2/io-form/io-form-min.js&2in3/2.9.0/build/yui2-treeview/yui2-treeview-min.js&3.17.2/cookie/cookie-min.js&3.17.2/array-extras/array-extras-min.js&3.17.2/array-invoke/array-invoke-min.js&3.17.2/arraylist/arraylist-min.js&3.17.2/model/model-min.js&3.17.2/model-list/model-list-min.js&3.17.2/datatable-core/datatable-core-min.js&3.17.2/view/view-min.js&3.17.2/datatable-head/datatable-head-min.js&3.17.2/datatable-body/datatable-body-min.js&3.17.2/datatable-table/datatable-table-min.js&3.17.2/datatable-base/datatable-base-min.js&3.17.2/datatable-column-widths/datatable-column-widths-min.js&3.17.2/datatable-message/lang/datatable-message_en.js:58:287)
    at e.Subscriber._notify (https://example.com/theme/yui_combo.php?rollup/3.17.2/yui-moodlesimple-min.js:40:51)
    at e.Subscriber.notify (https://example.com/theme/yui_combo.php?rollup/3.17.2/yui-moodlesimple-min.js:40:245)
    at e.CustomEvent._notify (https://example.com/theme/yui_combo.php?rollup/3.17.2/yui-moodlesimple-min.js:39:4257)
    at e.CustomEvent._procSubs (https://example.com/theme/yui_combo.php?rollup/3.17.2/yui-moodlesimple-min.js:39:4916)
```

- **Check nginx error log** /var/log/nginx/error.log

if error content :
> 1. open() "/var/lib/nginx/tmp/client_body/*" failed (13: Permission denied) [gotolink](https://github.com/sanekmihailow/ERRORS-Cathed/blob/main/application%20errors/Web%20servers/nginx/2022/09/failed%20open()%20%22var%5Clib%5Cnginx%5Ctmp%5Cclient_body%5C0000000025%22.md)

```
2022/09/08 12:54:05 [crit] 417525#0: *1716 open() "/var/lib/nginx/tmp/client_body/0000000025" failed (13: Permission denied), client: 1.1.1.1, server: example.com, request: "POST /repository/repository_ajax.php?action=upload HTTP/2.0", host: "example.com", referrer: "https://example.com/user/files.php"
```
