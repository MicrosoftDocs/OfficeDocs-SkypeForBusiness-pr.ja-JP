---
title: 'Lync Server 2013: 応答グループ構成のアクセス許可と前提条件'
description: 'Lync Server 2013: 応答グループ構成のアクセス許可と前提条件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7a0548c1d8886eb7741d1a31b24b480c1a2d30f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560903"
---
# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Lync Server 2013 での応答グループ構成のアクセス許可と前提条件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-05_

応答グループはエンタープライズ VoIP 通話管理機能です。 このトピックでは、応答グループを構成する前に準備する必要のある事項、および構成タスクの実行に必要な管理者資格情報とアクセス許可について説明します。

このセクションでは、応答グループに関わる計画ドキュメントを読んでいることが前提となります。 詳細については、「計画」のドキュメントの「 [Lync Server 2013 の通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md) 」を参照してください。

<div>

## <a name="configuration-tools-and-administrative-roles"></a>構成ツールと管理役割

以下の管理ツールを使用して応答グループを構成できます。

  - Lync Server コントロール パネル

  - 応答グループ構成ツール

  - Lync Server 管理シェル

応答グループを構成するには、次の管理役割のうち 1 つ以上のメンバーになる必要があります。


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Active Directory セキュリティ グループ (1)</strong></p></td>
<td><p>ワークフローの作成</p></td>
<td><p>マネージャーの割り当て</p></td>
<td><p>エージェント、キューの作成/割り当て</p></td>
<td><p>休日と営業時間の作成/管理</p></td>
<td><p>ワークフローのアクティブ化/非アクティブ化</p></td>
<td><p>ワークフローの構成 (IVR またはハント グループ)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>√ (2)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> Active Directory ドメインサービスのユーザーオブジェクトは、リストされている指定された active directory セキュリティグループのメンバーである必要があります。 セキュリティグループにユーザーを追加するための適切なアクセス許可を持つ管理者またはその他の委任された Active Directory グループメンバー (たとえば、管理者、アカウントオペレーター) は、ユーザーオブジェクトを一覧に表示されているセキュリティグループまたはグループに追加する必要があります。 <STRONG>(2)</STRONG> CsResponseGroupAdministrator が Csresponsegroupadministrator に割り当てたワークフローに対してのみ。 <STRONG>(3)</STRONG> 応答グループマネージャーは、現在の管理者が既に管理しているワークフローに、CsResponseGroupManager の別のメンバーを割り当てることができます。 <STRONG>(4)</STRONG> csviewonlyadministrator は、Verb "Get" Lync Server 管理シェルコマンドレットのみを実行できます。



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>応答グループ構成の前提条件

応答グループでは、以下のコンポーネントが必要です。

  - アプリケーション サービス

  - 応答グループ アプリケーション

  - 言語パック

  - ファイル ストア (オーディオ ファイルを格納)

  - Web サービス (応答グループ構成ツールとエージェントのサインインおよびサインアウトコンソールを含む)

これらのコンポーネントはすべて、エンタープライズ VoIP を展開するときに既定でインストールされます。

応答グループを構成する前に、次のタスクを実行する必要がある場合があります。

  - Lync Server 2013 およびエンタープライズ Voip に対してユーザーを有効にします。

  - Federal Information Processing Standards (FIPS) に準拠するように構成ファイルを変更します。

  - キュー名やエージェント グループ名で Yi、Meng、および Zang の文字がサポートされるようにデータベースの照合順序を変更します。

<div>

## <a name="enabling-users"></a>ユーザーの有効化

応答グループを構成する最初の手順は、エージェントグループを作成することです。 エージェントグループを作成する前に、Lync Server 2013 およびエンタープライズ Voip の応答グループのエージェントになるユーザーを有効にする必要があります。 Lync Server 2013 に対するユーザーの有効化は、通常、Enterprise Edition サーバーまたは Standard Edition サーバーの展開の手順です。 Lync Server 2013 でユーザーを有効にする方法の詳細については、「 [Lync server 2013 のユーザーアカウントの無効化または再有効化](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)」を参照してください。 エンタープライズ VoIP のユーザーの有効化は通常、エンタープライズ VoIP 展開で行うステップです。 詳細については、「 [Lync Server 2013 のエンタープライズ voip でユーザーを有効にする](lync-server-2013-enable-users-for-enterprise-voice.md)」を参照してください。

</div>

<div>

## <a name="complying-with-fips-requirements"></a>FIPS 要件の準拠

このセクションは、組織が FIPS (Federal Information Processing Standards) に準拠する必要がある場合にのみ参照してください。

FIPS に準拠するには、Web サービスをインストールした後で、別の暗号化アルゴリズムを使用するようにアプリケーションレベルの Web.config ファイルを変更する必要があります。 ASP.NET では、ビューステートデータを処理するためにトリプルデータ暗号化標準 (3DES) アルゴリズムを使用するように指定する必要があります。 応答グループアプリケーションの場合、この要件は応答グループ構成ツールと、エージェントのサインインおよびサインアウトコンソールに適用されます。 この要件の詳細については、「Microsoft サポート技術情報の記事911722」を参照してください。 ASP.NET 1.1 から ASP.NET 2.0 にアップグレードした後に ViewState が有効になっている ASP.NET web ページにアクセスすると、エラーメッセージが表示されることがあり [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183) ます。

Web.config ファイルを変更するには、以下の手順を実行します。

1.  メモ帳などのテキスト エディターで、アプリケーションレベルの Web.config ファイルを開きます。

2.  Web.config ファイルで、セクションを見つけ `<system.web>` ます。

3.  次の `<machineKey>` セクションをセクション内に追加し `<system.web>` ます。
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Web.config ファイルを保存します。

5.  コマンドプロンプトで次のコマンドを実行して、インターネットインフォメーションサービス (IIS) サービスを再起動します。
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Yi、Meng、および Zang の文字のサポート

このセクションは、組織で Yi、Meng、または Zang の文字をサポートする必要がある場合に参照してください。

<div>


> [!NOTE]  
> Yi、Meng、および Zang の文字の概要と、展開においてそれらが重要である理由については、GB18030 文字セットの情報を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A> 。



</div>

Yi、Meng、または Zang の文字をサポートするには、Rgsconfig データベースの照合順序を変更する必要があります。 各 Rgsconfig データベースの以下の表にある [**名前**] 列の照合順序を変更します。

  - dbo.AgentGroups

  - dbo.Microsoft.rtc.rgs.management.writablesettings.businesshours

  - dbo.HolidaySets

  - dbo.キュー

  - dbo.ワークフロー

SQL Server 2008 R2 および SQL Server 2012 の場合は、Latin \_ General \_ 100 (アクセントを区別する) の照合順序を使用します。 この照合順序を使用する場合は、どのオブジェクト名も大文字と小文字は区別されません。

照合順序は、Microsoft SQL Server Management Studio を使用して変更できます。 このツールの使用の詳細については、「」の「SQL Server Management Studio を使用する」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184) 。 照合順序を変更するには、以下の手順に従います。

1.  表の再作成を必要とする変更が SQL Server Management Studio で許可されていることを確認します。 詳細については、「」の「保存 (許可されない)」ダイアログボックスを参照してください [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186) 。 列の照合順序の設定の詳細については、「」の「How to: Set Column Collation (Visual Database Tools)」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185) 。

2.  Microsoft SQL Server Management Studio を使用して、Rgsconfig データベースに接続します。

3.  Rgsconfig データベースで変更したい表を見つけて右クリックし、[**設計**] をクリックします。

4.  [**名前**] 列の照合順序を変更して、表を保存します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

