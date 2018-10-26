---
title: 信頼されたアプリケーションの一覧の表示
TOCTitle: 信頼されたアプリケーションの一覧の表示
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48274070
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 信頼されたアプリケーションの一覧の表示

 

_**トピックの最終更新日:** 2012-09-21_

Lync Server 2013 コントロール パネルを使用して、Lync Server 2013 環境で展開した信頼されたアプリケーションの一覧を表示できます。信頼されたアプリケーションとは、Lync Server 2013 が信頼する Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションのことです。この信頼関係は、次のように要約されます。

  - 信頼されたアプリケーションは、Lync Server による認証でチャレンジされません。

  - 信頼されたアプリケーションは、SIP トランザクション、接続、または発信側のボイス オーバー IP (VoIP) 通話の場合に、Lync Server によって制限されません。

  - 信頼されたアプリケーションは、任意のユーザーの代理となり、名簿に記載されなくても会議に参加できます。

  - 信頼されたアプリケーションは、高い可用性と復元性を示します。

Lync Server コントロール パネル では、アプリケーションの名前、アプリケーションが実行されるプール、およびアプリケーションが使用するポートを表示できます。

## 信頼されたアプリケーションの一覧を表示するには

1.  CsServerAdministrator、CsAdministrator、CsHelpDesk、または CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。Lync Server 2013 で使用できる定義済みの管理者の役割の詳細については、「[Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**トポロジ**\] をクリックし、\[**信頼されたアプリケーション**\] をクリックします。

4.  \[**信頼されたアプリケーション**\] ページで、必要に応じて列の見出しをクリックし、アプリケーションを並べ替えます。

## 関連項目

#### その他のリソース

[Lync Server 2013 トポロジの管理](lync-server-2013-managing-the-lync-server-topology.md)

