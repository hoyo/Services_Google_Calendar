Services_Google_Calendar
========================

Google Calendar Data APIをラップしたPHPクラス(PEAR互換)です。

終日イベントのみ追加・削除・編集が可能です。

PHP4・PHP5のいずれでも利用可能です。



依存PEARパッケージ
------------------

* HTTP_Client
* XML_Serializer



使い方
------

### イベント情報を取得する

<pre>require_once 'Services/Google/Calendar.php';

// initialize
$gc = new Services_Google_Calendar();

// get events data
$public_data = $gc->getEvents($gmail_id);

// get events data (private mode)
$private_data = $gc->getEvents($gmail_id, $hash);</pre>

### イベントを追加する

<pre>require_once 'Services/Google/Calendar.php';

// initialize
$gc = new Services_Google_Calendar($gmail_id, $passwd);

// set event data
$entry['title']        = 'Event title';
$entry['content']      = 'Event description';
$entry['where']        = 'Where the event helds';
$entry['when'][0]      = '2006-10-20';
$entry['when'][1]      = '2006-10-24';
$entry['transparency'] = 'transparent';
$entry['visibility']   = 'private';

// add an event
$result = $gc->addEvent($entry);</pre>



