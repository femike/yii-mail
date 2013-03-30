yii-mail
========

yii-mail forck http://yii-mail.googlecode.com/svn/trunk/

Example config:
<pre>
  return array(
    ...
    'import => array(
      ...
      'ext.mail.YiiMailMessage',
    ),
      'components' => array(
        'mail' => array(
          'class' => 'ext.yii-mail.YiiMail',
          'transportType' => 'php',
          'viewPath' => 'application.views.mail',
          'logging' => true,
          'dryRun' => false
        ),
        ...
      )
  );
</pre>

Example usage:
<pre>
$message = new YiiMailMessage;
$message->setBody('Message content here with HTML', 'text/html');
$message->subject = 'My Subject';
$message->addTo('johnDoe@domain.com');
$message->from = Yii::app()->params[]'adminEmail'];
Yii::app()->mail->send($message);
</pre>
