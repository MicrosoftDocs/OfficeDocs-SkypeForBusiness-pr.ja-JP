---
title: Lync Server 2013 コントロール パネルのトラブルシューティング
TOCTitle: Lync Server 2013 コントロール パネルのトラブルシューティング
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48272116
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 コントロール パネルのトラブルシューティング

 

_**トピックの最終更新日:** 2016-12-08_

このトピックでは、Lync Server 2013 コントロール パネルへのアクセスをトラブルシューティングするときに役立つ情報と手順を示します。

## インターネット ブラウザーの要件

Lync Server コントロール パネルを使用するには、Microsoft Silverlight ブラウザー プラグイン バージョン 4.0.50524.0 以降がインストールされている必要があります。Silverlight がインストールされていない場合や、以前のバージョンがインストールされている場合は、メッセージ内の手順に従って必要なバージョンをインストールしてください。

> [!NOTE]
> Lync Server コントロール パネルの他のソフトウェア要件は、Lync Server コントロール パネルおよび他のすべての Lync Server 2013 管理ツールをインストールできるオペレーティング システムに関するものです。詳細については、「サポート」のドキュメントの「<a href="lync-server-2013-server-and-tools-operating-system-support.md">Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート</a>」を参照してください。


セキュリティ上の理由により、インターネット ブラウザーで Silverlight のインストールがブロックされる場合は、Lync Server コントロール パネルを開く URL (Uniform Resource Locator) を信頼済みサイトの一覧に追加します。Internet Explorer のセキュリティ設定で、\[**ActiveX コントロールとプラグインの実行**\] が \[**有効にする**\] に設定されていることを確認します。詳細については、[http://go.microsoft.com/fwlink/?linkid=214060\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=214060%26clcid=0x411) を参照してください。また、ブラウザーが SSL 3.0 を使用するように構成されていることも確認してください。

インターネット ブラウザーがプロキシ サーバーを使用するように構成されている場合、内部サイトとして自動検出されたサイトにはプロキシ サーバーを使用しない構成になっていることを確認します。または、プロキシ サーバーの構成設定で、アドレスをブラウザーの例外リストに追加します。

## 管理アクセス URL の DNS レコードおよび証明書の要件

Lync Server コントロール パネルにアクセスする簡易 URL を構成した場合は、その管理アクセス URL を使用するために必要な静的ドメイン ネーム システム (DNS) ホスト (A) のリソース レコードと証明書も構成済みであることを確認します。ベース URL を随時変更する場合は、その変更が適切な DNS レコードと証明書に反映されていることを確認し、各ディレクターとフロント エンド サーバーで *Enable-CsComputer* を実行して変更を必ず登録します。詳細については、「計画」のドキュメントの以下のトピックを参照してください。

  - [Lync Server 2013 での簡単な URL の計画](lync-server-2013-planning-for-simple-urls.md)

  - [Lync Server 2013 の簡易 URL の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013 の内部サーバーに対する証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)

管理アクセス URL を構成するための操作手順については、「展開」のドキュメントの「[Lync Server 2013 での簡単な URL の編集または構成](lync-server-2013-edit-or-configure-simple-urls.md)」を参照してください。

> [!NOTE]
> Web サーバーに複数のネットワーク アダプターが装着されている場合は、DNS 解決が正しく機能するように、追加のネットワーク アダプターごとに DNS を手動で構成する必要があります。


## インターネット インフォメーション サービス (IIS) の要件

Lync Server コントロール パネルは、インターネット インフォメーション サービス (IIS) を必要とする Lync Server 2013 のコンポーネントの 1 つです。特に、HTTP リダイレクト機能と Windows 認証機能が有効になっていること、および World Wide Web 発行サービス (W3SVC) が実行されていることを確認してください。

## World Wide Web 発行サービス (Windows サービス) への依存

World Wide Web 発行サービスが停止していると、Lync Server コントロール パネルにアクセスできません。サービスを再起動するには、Windows サービス Microsoft 管理コンソール (MMC) を使用します。

**World Wide Web 発行サービスを開始するには**

1.  World Wide Web 発行サービスがインターネット インフォメーション サービス (IIS) の一部としてインストールされているコンピューターにログオンします。

2.  \[**スタート**\] ボタンをクリックし、\[**管理ツール**\] をクリックして、\[**サービス**\] をクリックします。

3.  \[**World Wide Web 発行サービス**\] を右クリックし、\[**開始**\] をクリックします。

## アプリケーション プール モード

CsManagementAppPool アプリケーション プールがネットワーク サービス アカウントをプロセス モデル ID として使用するように IIS を構成します。

## ユーザー権限およびアクセス許可

Lync Server コントロール パネルにサインインするには、CsAdministrator グループのメンバーであるドメイン アカウントを使用するか、管理者がユーザー権限とアクセス許可を委任したアカウントを使用する必要があります。ローカル コンピューターのアカウントを使用して Lync Server コントロール パネルにサインインすることはできません。役割ベースのアクセス制御 (RBAC) による管理タスクの委任の詳細については、「計画」のドキュメントの「[Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。

簡易 URL を使用して Lync Server コントロール パネルにアクセスする場合は、Web サーバーが RTCUniversalServerAdmins グループおよび RTCUniversalUserAdmins グループに追加されていることを確認してください。

## 関連項目

#### 概念

[Lync Server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md)

