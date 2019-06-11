---
title: 'Lync Server 2013: カテゴリ別の Lync Server コマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c7a5e0b3fa81d6730caed1f4ce2f89adf0d7d96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a>カテゴリ別の Lync Server 2013 コマンドレット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-09-20_

Microsoft Lync Server 2013 には、ほとんどの550コマンドレットが付属しており、管理者が Lync Server をコマンドラインから管理できるように設計されています。 Lync Server 管理シェルからコマンドレットにアクセスします。 コマンドラインからコマンドレットのヘルプを直接取得するには、次のようなコマンドを入力します。

    Get-Help New-CsVoicePolicy -Full

上のコマンドを実行すると、 **CsVoicePolicy**コマンドレットで利用できるすべてのヘルプが取得されます。 ヘルプを取得するコマンドレットの名前を使用して、参照を**新しい CsVoicePolicy**に置き換えます。

Microsoft Lync Server 2013 を管理するために使用できるコマンドレットの完全な一覧を取得するには、Lync Server 管理シェルのコマンドプロンプトで次のように入力します。

    Get-Command * -Module Lync -CommandType cmdlet

必要なコマンドレットがわからない場合は、コマンドレットとヘルプトピックのカテゴリ別の一覧も提供しています。 いくつかのコマンドレットが複数のカテゴリに表示されることがわかります。これは、製品の複数の領域に適用されるためです。 カテゴリの一覧を次に示します。

<div>


> [!NOTE]
> Skype for Business コマンドレットリファレンスは docs.microsoft.com に移動されました。 以下のリンクをクリックすると、新しい docs.microsoft.com ページに移動します。 これでコンテンツが公開され、GitHub を通じてコミュニティの投稿に使用できるようになりました。 投稿に興味をお持ちですか? ここでは、リポジトリ内の README を確認します。<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

<div>

## <a name="in-this-section"></a>このセクション中


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-user-management-cmdlets.md">Lync Server 2013 のユーザー管理コマンドレット</a></p></td>
<td><p><a href="lync-server-2013-voice-application-cmdlets.md">Lync Server 2013 の音声アプリケーションコマンドレット</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-client-management-cmdlets.md">Lync Server 2013 のクライアント管理コマンドレット</a></p></td>
<td><p><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Lync Server 2013 の高度なエンタープライズボイスコマンドレット</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-im-and-presence-cmdlets.md">Lync Server 2013 の IM とプレゼンスのコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Lync Server 2013 の PSTN 接続コマンドレット</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencing-cmdlets.md">Lync Server 2013 での会議コマンドレット</a></p></td>
<td><p><a href="lync-server-2013-phones-and-devices-cmdlets.md">Lync Server 2013 の電話とデバイスのコマンドレット</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Lync Server 2013 のインフラストラクチャと展開コマンドレット</a></p></td>
<td><p><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Lync Server 2013 での移行と共存のコマンドレット</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-security-cmdlets.md">Lync Server 2013 のセキュリティコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync server 2013 の lync Server 管理シェル構成コマンドレット</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Lync Server 2013 のサーバーの役割とサービスコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-mobility-cmdlets.md">Lync Server 2013 のモバイルコマンドレット</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-application-management-cmdlets.md">Lync Server 2013 のアプリケーション管理コマンドレット</a></p></td>
<td><p><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Lync Server 2013 の常設チャットサーバーコマンドレット</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Lync Server 2013 のフェデレーションと外部アクセスコマンドレット</a></p></td>
<td><p><a href="lync-server-2013-centralized-logging-cmdlets.md">Lync Server 2013 の集中化されたログコマンドレット</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-enterprise-voice-cmdlets.md">Lync Server 2013 のエンタープライズボイスコマンドレット</a></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server PowerShell ブログ](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

