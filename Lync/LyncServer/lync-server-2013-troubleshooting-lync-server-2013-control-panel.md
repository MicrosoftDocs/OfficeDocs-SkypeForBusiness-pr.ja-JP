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
ms.openlocfilehash: ff82a1e63a064d0053fc77614d6a9b5fa818c23e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルのトラブルシューティング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-07-28_

このトピックでは、Lync Server 2013 コントロールパネルへのアクセスのトラブルシューティングに役立つ情報と手順について説明します。

<div>

## <a name="internet-browser-requirements"></a>インターネットブラウザーの要件

Lync Server コントロールパネルでは、Microsoft Silverlight ブラウザープラグインバージョン4.0.50524.0 または最新バージョンがインストールされている必要があります。 Silverlight がインストールされていない場合、または以前のバージョンがインストールされている場合は、メッセージの指示に従って必要なバージョンをインストールします。

<div>


> [!NOTE]  
> Lync Server コントロールパネルのその他のソフトウェア要件は、Lync Server コントロールパネルとその他のすべての Lync Server 2013 管理ツールをインストールできるオペレーティングシステムに関連しています。 詳細については、サポートドキュメントの「 <A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート</A>」を参照してください。



</div>

セキュリティ上の理由により、インターネットブラウザーで Silverlight のインストールがブロックされている場合は、[Lync Server] コントロールパネルを開くための Uniform Resource Locator (URL) を信頼済みサイトの一覧に追加します。 Internet Explorer の [セキュリティ設定] で、[ **ActiveX コントロールとプラグインの実行**] が [**有効**] に設定されていることを確認します。 詳細について[http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)は、を参照してください。 さらに、ブラウザーが SSL 3.0 を使用するように構成されていることを確認します。

インターネットブラウザーがプロキシサーバーを使用するように構成されている場合は、内部サイトとして自動的に検出されるサイトのプロキシサーバーを経由しないようにブラウザーが構成されていることを確認します。 または、プロキシサーバーの構成設定で、ブラウザーの例外リストにアドレスを追加します。

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>管理アクセス URL の DNS レコードと証明書の要件

Lync Server コントロールパネルにアクセスするための単純な URL を構成している場合は、その管理アクセス URL を使用するために必要な静的ドメインネームシステム (DNS) のリソースレコードと証明書も構成していることを確認します。 ベース URL をいつでも変更する場合は、適切な DNS レコードと証明書に変更が反映されていることを確認します。また、各ディレクターとフロントエンドサーバー上のユーザーがこの変更を登録*するように*します。 詳細については、計画ドキュメントの次のトピックを参照してください。

  - [Lync Server 2013 での簡単な URL の計画](lync-server-2013-planning-for-simple-urls.md)

  - [Lync Server 2013 の簡易 URL の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013 の内部サーバーに対する証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)

管理アクセス URL を構成するための詳しい手順については、展開ドキュメントの「 [Lync Server 2013 での単純な url の編集または構成](lync-server-2013-edit-or-configure-simple-urls.md)」を参照してください。

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>インターネットインフォメーションサービス (IIS) の要件

Lync Server コントロールパネルは、インターネットインフォメーションサービス (IIS) を必要とする、Lync Server 2013 のコンポーネントの1つです。 特に、HTTP リダイレクションと Windows 認証機能が有効であり、World Wide Web 発行サービス (W3SVC) が実行されていることを確認します。

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>World Wide 発行サービス (Windows サービス) の依存関係

World Wide Web 発行サービスが停止すると、Lync Server コントロールパネルにアクセスできなくなります。 Windows Services Microsoft 管理コンソール (MMC) を使用してサービスを再起動することができます。

**World Wide Web 発行サービスを開始するには**

1.  World Wide Web 発行サービスがインターネットインフォメーションサービス (IIS) の一部としてインストールされているコンピューターにログオンします。

2.  [**スタート**] をクリックし、[**管理ツール**] をクリックして、[**サービス**] をクリックします。

3.  [ **World Wide Web 発行サービス**] を右クリックし、[**開始**] をクリックします。

</div>

<div>

## <a name="application-pool-mode"></a>アプリケーションプールモード

CsManagementAppPool アプリケーションプールがプロセスモデル id としてネットワークサービスアカウントを使用できるように IIS を構成します。

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>ユーザー権利と権限

CsAdministrator グループのメンバーであるドメインアカウントを使用するか、ユーザー権利と権限を委任しているアカウントを使用して、Lync Server コントロールパネルにサインインする必要があります。 ローカルコンピューターアカウントを使用して、Lync Server コントロールパネルにサインインすることはできません。 ロールベースのアクセス制御 (RBAC) による管理タスクの委任について詳しくは、計画ドキュメントの「 [Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」をご覧ください。

簡単な URL を使用して Lync Server コントロールパネルにアクセスする場合は、web サーバーが RTCUniversalServerAdmins グループと RTCUniversalUserAdmins グループに追加されていることを確認します。

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

