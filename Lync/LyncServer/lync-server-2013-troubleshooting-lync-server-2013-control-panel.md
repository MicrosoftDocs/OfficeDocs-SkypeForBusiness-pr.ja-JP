---
title: 'Lync Server 2013: Lync Server 2013 コントロールパネルのトラブルシューティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da23bc56d18b1b5e6235551f7b99cc15e658fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535934"
---
# <a name="troubleshooting-lync-server-2013-control-panel"></a>Lync Server 2013 コントロール パネルのトラブルシューティング

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-07-28_

このトピックでは、Lync Server 2013 コントロールパネルへのアクセスのトラブルシューティングに役立つ情報と手順について説明します。

<div>

## <a name="internet-browser-requirements"></a>インターネット ブラウザーの要件

Lync Server コントロールパネルでは、Microsoft Silverlight ブラウザープラグインバージョン4.0.50524.0 または最新バージョンがインストールされている必要があります。 Silverlight がインストールされていない場合、または以前のバージョンがインストールされている場合は、メッセージの指示に従って必要なバージョンをインストールします。

<div>


> [!NOTE]  
> Lync server コントロールパネルの他のソフトウェア要件は、Lync Server コントロールパネルとその他のすべての Lync Server 2013 管理ツールをインストールできるオペレーティングシステムに関連しています。 詳細については、「サポート」のドキュメントの「 <A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート</A> 」を参照してください。



</div>

セキュリティ上の理由から、インターネットブラウザーが Silverlight のインストールをブロックする場合は、Lync Server コントロールパネルを開く URL (Uniform Resource Locator) を信頼済みサイトの一覧に追加します。 Internet Explorer のセキュリティ設定で、[**ActiveX コントロールとプラグインの実行**] が [**有効にする**] に設定されていることを確認します。 詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060) 。 また、ブラウザーが SSL 3.0 を使用するように構成されていることも確認してください。

インターネット ブラウザーがプロキシ サーバーを使用するように構成されている場合、内部サイトとして自動検出されたサイトにはプロキシ サーバーを使用しない構成になっていることを確認します。または、プロキシ サーバーの構成設定で、アドレスをブラウザーの例外リストに追加します。

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>管理アクセス URL の DNS レコードおよび証明書の要件

Lync Server コントロールパネルにアクセスするための簡単な URL を構成した場合は、その管理アクセス URL を使用するために必要な静的ドメインネームシステム (DNS) ホスト (A) リソースレコードと証明書も構成してください。 ベース URL をいつでも変更する場合は、変更が適切な DNS レコードと証明書に反映されていることと、各ディレクターおよびフロントエンドサーバーで、 *CsComputer* を実行して変更を登録していることを確認してください。 詳細については、「計画」のドキュメントの以下のトピックを参照してください。

  - [Lync Server 2013 での簡単な Url の計画](lync-server-2013-planning-for-simple-urls.md)

  - [Lync Server 2013 の簡易 Url の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)

管理アクセス URL を構成するための詳しい手順については、「展開」のドキュメントの「 [Edit or configure Simple URLs In Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) 」を参照してください。

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>インターネット インフォメーション サービス (IIS) の要件

Lync Server コントロールパネルは、インターネットインフォメーションサービス (IIS) を必要とする Lync Server 2013 のコンポーネントの1つです。 特に、HTTP リダイレクト機能と Windows 認証機能が有効になっていること、および World Wide Web 発行サービス (W3SVC) が実行されていることを確認してください。

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>World Wide Web 発行サービス (Windows サービス) への依存

World Wide Web Publishing Service を停止すると、Lync Server コントロールパネルにアクセスできなくなります。 サービスを再起動するには、Windows サービス Microsoft 管理コンソール (MMC) を使用します。

**World Wide Web 発行サービスを開始するには**

1.  World Wide Web Publishing Service がインストールされているコンピューターに、インターネットインフォメーションサービス (IIS) の一部としてログオンします。

2.  [**スタート**] ボタンをクリックし、[**管理ツール**] をクリックして、[**サービス**] をクリックします。

3.  [**World Wide Web 発行サービス**] を右クリックし、[**開始**] をクリックします。

</div>

<div>

## <a name="application-pool-mode"></a>アプリケーション プール モード

CsManagementAppPool アプリケーション プールがネットワーク サービス アカウントをプロセス モデル ID として使用するように IIS を構成します。

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>ユーザー権限およびアクセス許可

Lync Server コントロールパネルにサインインするには、CsAdministrator グループのメンバーであるドメインアカウントを使用するか、委任されたユーザー権限とアクセス許可を持つアカウントを使用する必要があります。 ローカルコンピューターのアカウントを使用して Lync Server コントロールパネルにサインインすることはできません。 役割ベースのアクセス制御 (RBAC) による管理タスクの委任の詳細については、「計画」のドキュメントの「 [Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md) 」を参照してください。

簡単な URL を使用して Lync Server コントロールパネルにアクセスする場合は、web サーバーが RTCUniversalServerAdmins および RTCUniversalUserAdmins グループに追加されていることを確認してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

