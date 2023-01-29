# Smartyのテンプレート関数プラグインで配列を作成

```php
// テンプレート
{person_list users=users}
{foreach from=$users item=user}
<ul>
    <li>{$user.id}</li>
    <li>{$user.name}</li>
    <li>{$user.txt}</li>
</ul>
{/foreach}

// テンプレート関数プラグイン
/*
 * Smarty plugin
 * -------------------------------------------------------------
 * File:     function.person_list.php
 * Type:     function
 * Name:     person_list
 * Purpose:  人物リストを作成
 * -------------------------------------------------------------
 */
function smarty_function_person_list($params, $template)
{
    $list = array(
        array('id' => 'katakana', 'name' => 'ナマエ', 'txt' => 'テキスト'),
        array('id' => 'hiragana', 'name' => 'なまえ', 'txt' => 'てきすと'),
        array('id' => 'kanji', 'name' => '名前', 'txt' => '文章'),
    );
    $template->assign($params['users'], $list); 
}
```

## 参考サイト
- [php - Using plugin functions in Smarty foreach - Stack Overflow](https://stackoverflow.com/questions/19510189/using-plugin-functions-in-smarty-foreach)
- [Template Functions | Smarty](https://www.smarty.net/docs/en/plugins.functions.tpl)