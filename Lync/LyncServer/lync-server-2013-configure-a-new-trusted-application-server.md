---
title: Lync Server 2013 での信頼された新しいアプリケーション サーバーの構成
TOCTitle: Lync Server 2013 での信頼された新しいアプリケーション サーバーの構成
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48273173
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での信頼された新しいアプリケーション サーバーの構成

 

_**トピックの最終更新日:** 2016-12-08_

信頼されたアプリケーションとは、Microsoft Lync Server 2013 に信頼されている、Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションです。UCMA アプリケーションの詳細については、「Unified Communications Managed API 3.0 Core SDK」ドキュメント ([http://go.microsoft.com/fwlink/?linkid=210320\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=210320%26clcid=0x411)) を参照してください。

Microsoft Outlook Web Access (OWA) および Lync Server 2013 の構成の詳細については、Microsoft Exchange Server 2013 のドキュメントの「Outlook Web App と Lync Server 2010 の統合の構成」を参照してください。

サーバーの役割を追加または削除するときにトポロジを正常に公開、有効化、または無効化するには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログオンする必要があります。サーバーの役割を追加するための、適切な管理者アクセス許可および権限を委任することもできます。詳細については、「展開」のドキュメントの「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。他の構成変更の場合は、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。

## 信頼されたアプリケーション サーバーを構成するには

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジ ビルダーを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server トポロジ ビルダー**\] の順にクリックします。

3.  \[**既存の展開からトポロジをダウンロードする**\] を選択し、\[**OK**\] をクリックします。

4.  \[**トポロジに名前を付けて保存**\] ダイアログ ボックスで、トポロジ ビルダーのファイルをクリックし、\[**保存**\] をクリックします。

5.  左側のウィンドウで、\[**信頼済みアプリケーション サーバー**\] を右クリックし、\[**新しい信頼済みアプリケーション プール**\] をクリックします。

6.  信頼されたアプリケーション プールの \[**プールの FQDN**\] を入力してから、単一サーバーにするか複数サーバーにするかを選択し、\[**次へ**\] をクリックします。

7.  \[**次ホップの選択**\] ページで、ボックスの一覧の \[Lync Server 2013 フロント エンド プール\] を選択します。

8.  \[**完了**\] をクリックします。

9.  最上位ノードの \[**Lync Server 2013**\] を選択し、\[**操作**\] メニューの \[**トポロジの公開**\] をクリックします。
    
    \[**信頼済みアプリケーション プール**\] は、正しく作成されて、適切なフロント エンド プールに関連付けられている必要があります。

