---
title: 'Lync Server 2013: リバース プロキシ経由のアクセスを確認する'
TOCTitle: リバース プロキシ経由のアクセスを確認する
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48271657
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でリバース プロキシ経由のアクセスを確認する

 

_**トピックの最終更新日:** 2013-03-29_

以下の手順に従って、ユーザーがリバース プロキシ上の情報にアクセスできることを確認します。 正しくアクセスできるようにするには、ファイアウォール構成とドメイン ネーム システム (DNS) 構成を完了する必要がある場合があります。

## インターネット経由で Web サイトにアクセスできることを確認するには

  - Web ブラウザーを開き、アドレス帳ファイルや会議用の Web サイトにアクセスする際にクライアントが使用する URL を \[**アドレス**\] バーに入力します。以下に例を示します。
    
      - アドレス帳サーバーの場合、入力する URL は、**https:// *externalwebfarmFQDN*/abs** のようになります (*externalwebfarmFQDN* は、アドレス帳サービスをホストする外部 Web サービスの外部 FQDN)。ユーザーは HTTP チャレンジを受信する必要があります。これは、アドレス帳サーバー フォルダーのディレクトリ セキュリティが、既定で Windows 認証に構成されているためです。
    
      - 会議の場合、入力する URL は、**https:// *externalwebfarmFQDN*/meet** のようになります (*externalwebfarmFQDN* は、会議コンテンツをホストする Web ファームの外部 FQDN)。この URL には、会議のトラブルシューティングのページが表示されます。または、会議用の簡易 URL が正常に動作することを確認します。https://meet.contoso.com などが、会議参加用の簡易 URL の例です。
    
      - 配布グループ拡張の場合、入力する URL は、**https:// *externalwebfarmFQDN*/GroupExpansion/service.svc** のようになります。ユーザーは HTTP チャレンジを受信する必要があります。これは、配布グループ拡張サービスが、既定で Windows 認証に構成されているためです。
    
      - ダイヤルインの場合、入力する簡易 URL は、**https:// *externalwebfarmFQDN*/dialin** のようになります (*externalwebfarmFQDN* は、ダイヤルイン会議のダイヤルイン ページをホストする Web ファームの外部 FQDN)。ユーザーはダイヤルインのページに進みます。または、簡易 URL でのダイヤルインが正常に動作することを確認します。https://dialin.contoso.com などが、ダイヤルイン用の簡易 URL の例です。
    
      - 自動検出 URL が機能していることを確認するには、「https://lyncdiscover. *externaldomainFQDN* 」と入力します。ブラウザーでファイルを開くメッセージが表示されます。メモ帳を選んでファイルを開きます。一般的な応答は次のようになります。
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

