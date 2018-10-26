---
title: Office Communications Server 2007 R2 エッジ サーバーへの接続を承認する
TOCTitle: Office Communications Server 2007 R2 エッジ サーバーへの接続を承認する
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48271357
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Office Communications Server 2007 R2 エッジ サーバーへの接続を承認する

 

_**トピックの最終更新日:** 2012-09-28_

パイロット プール内の各 Lync Server 2013 フロントエンド サーバーまたは Standard Edition サーバーについて、Office Communications Server 2007 R2 エッジ サーバーへの接続が承認された内部サーバーのリストを更新する必要があります。更新しないと、従来のエッジ サーバーを使用して参加するユーザーに対する外部音声ビデオ (A/V) 会議が動作しません。

## Office Communications Server 2007 R2 エッジ サーバーへの接続を承認するには

1.  Office Communications Server 2007 R2 エッジ サーバーの \[**管理ツール**\] グループから \[**コンピューターの管理**\] スナップインを開きます。

2.  コンソール ツリーで \[**サービスとアプリケーション**\] を展開します。

3.  \[**Office Communications Server 2007 R2**\] を右クリックし、\[**プロパティ**\] をクリックします。

4.  \[**内部**\] タブをクリックします。

5.  \[**サーバーの追加**\] で \[**追加**\] をクリックします。

6.  \[**Office Communications Server の追加**\] ダイアログ ボックスで、適切な情報を入力します。
    
      - 各 Lync Server 2013 フロントエンド サーバーまたは Standard Edition サーバー、および Lync Server 2013 プールの完全修飾ドメイン名 (FQDN) を指定します。
    
      - 次ホップ コンピューターを FQDN で指定する静的ルートをプールに設定した場合、Lync Server 2013 ディレクターの FQDN を指定します。

7.  各 Lync Server 2013、フロントエンド サーバー、Standard Edition サーバー、プール、およびディレクターのエントリを追加したら、\[ **適用**\] をクリックし、\[**OK**\] をクリックしてプロパティ ページを閉じます。

