---
title: 'Lync Server 2013: 応答グループ構成のアクセス許可と前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Lync Server 2013 の応答グループ構成のアクセス許可と前提条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-05_

応答グループは、エンタープライズの音声通話管理機能です。 このトピックでは、応答グループを構成し、構成タスクを実行するために必要な管理資格情報とアクセス許可を構成するために必要な準備について説明します。

このセクションでは、回答グループに関連する計画ドキュメントを読み取っていることを前提としています。 詳細については、計画ドキュメントの「 [Lync Server 2013 での通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照してください。

<div>

## <a name="configuration-tools-and-administrative-roles"></a>構成ツールと管理者ロール

応答グループを構成するには、次の管理ツールを使用できます。

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
<td><p>√(2)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
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
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> Active Directory ドメインサービスのユーザーオブジェクトは、一覧表示されている指定の active directory セキュリティグループのメンバーである必要があります。 セキュリティグループにユーザーを追加するための適切な権限を持つ管理者またはその他の委任された Active Directory グループのメンバー (管理者、アカウントオペレーターなど) には、ユーザーが次のことをできるように、一覧表示されたセキュリティグループまたはグループにユーザーオブジェクトを追加する必要があります。記載されている関数を実行します。 <STRONG>(2)</STRONG> Csresponsegroupadministrator に割り当てられているワークフローのみ。 <STRONG>(3)</STRONG>応答グループマネージャーは、現在の管理者が既に管理しているワークフローに、CsResponseGroupManager の別のメンバーを割り当てることができます。 <STRONG>(4)</STRONG> csviewonlyadministrator は動詞 "Get" Lync Server 管理シェルコマンドレットのみを実行できます。



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>応答グループの構成の前提条件

応答グループには次のコンポーネントが必要です。

  - アプリケーション サービス

  - 応答グループ アプリケーション

  - 言語パック

  - ファイル ストア (オーディオ ファイルを格納)

  - Web サービス (応答グループの構成ツールとエージェントのサインインとサインアウトコンソールが含まれます)

エンタープライズボイスを展開すると、これらのすべてのコンポーネントが既定でインストールされます。

応答グループを構成する前に、次のタスクを実行する必要がある場合があります。

  - Lync Server 2013 およびエンタープライズ Voip のユーザーを有効にします。

  - Federal Information Processing Standards (FIPS) に準拠するように構成ファイルを変更します。

  - キュー名やエージェント グループ名で Yi、Meng、および Zang の文字がサポートされるようにデータベースの照合順序を変更します。

<div>

## <a name="enabling-users"></a>ユーザーの有効化

応答グループを構成するための最初の手順は、エージェントグループを作成することです。 エージェントグループを作成する前に、Lync Server 2013 およびエンタープライズ Voip の返信グループに対してエージェントとなるユーザーを有効にする必要があります。 Lync Server 2013 でユーザーを有効にするには、通常、Enterprise Edition server または Standard Edition server の展開の手順を実行します。 Lync Server 2013 でユーザーを有効にする方法の詳細については、「 [Lync server 2013 のユーザーアカウントを無効にする、または再度有効にする](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)」を参照してください。 エンタープライズ Voip のユーザーを有効にするには、通常、エンタープライズ Voip 展開の手順を使用します。 詳細については、「 [Lync Server 2013 でエンタープライズ voip のユーザーを有効にする](lync-server-2013-enable-users-for-enterprise-voice.md)」を参照してください。

</div>

<div>

## <a name="complying-with-fips-requirements"></a>FIPS 要件の準拠

このセクションは、組織が FIPS (Federal Information Processing Standards) に準拠する必要がある場合にのみ参照してください。

FIPS に準拠するには、Web サービスをインストールした後に別の暗号化アルゴリズムを使用するようにアプリケーションレベルの web.config ファイルを変更する必要があります。 ASP.NET で、トリプルデータ暗号化標準 (3DES) アルゴリズムを使ってビューステートデータを処理するように指定する必要があります。 応答グループアプリケーションの場合、この要件は、応答グループ構成ツールと、エージェントのサインインとサインアウトコンソールに適用されます。 この要件の詳細については、「Microsoft サポート技術情報の記事 911722 "ASP.NET 1.1 から ASP.NET 2.0" にアップグレードした後に ViewState が有効になっている ASP.NET web ページに[http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)アクセスすると、エラーメッセージが表示されることがあります。

Web.config ファイルを変更するには、以下の手順を実行します。

1.  メモ帳などのテキスト エディターで、アプリケーションレベルの Web.config ファイルを開きます。

2.  Web.config ファイルで、 `<system.web>`セクションを見つけます。

3.  `<system.web>`セクションのに次`<machineKey>`のセクションを追加します。
    
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
> Yi、Meng、および Zang 文字の概要と、それらが展開にとって重要である理由については、「GB18030 文字セット<A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>」の情報を参照してください。



</div>

Yi、Meng、または Zang の文字をサポートするには、Rgsconfig データベースの照合順序を変更する必要があります。各 Rgsconfig データベースの以下のテーブルにある [**名前**] 列の照合順序を変更します。

  - dbo.AgentGroups

  - dbo.BusinessHours

  - dbo.HolidaySets

  - dbo.Queues

  - dbo.Workflows

SQL Server 2008 R2 および SQL Server 2012 の場合は、Latin\_General\_100 (アクセントに依存) の照合順序を使用します。 この照合順序を使用する場合は、どのオブジェクト名も大文字と小文字は区別されません。

照合順序は、Microsoft SQL Server Management Studio を使用して変更できます。 このツールの使用方法の詳細については、の「SQL Server [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)Management Studio を使用する」を参照してください。 照合順序を変更するには、以下の手順に従います。

1.  テーブルの再作成を必要とする変更が SQL Server Management Studio で許可されていることを確認します。 詳細については、「[保存 (許可されて[http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)いません)] ダイアログボックス」を参照してください。 列の照合順序の設定の詳細については、「」の「方法: 列の[http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)照合順序を設定する (Visual Database Tools)」を参照してください。

2.  Microsoft SQL Server Management Studio を使用して、Rgsconfig データベースに接続します。

3.  Rgsconfig データベースで変更したいテーブルを見つけて右クリックし、[**設計**] をクリックします。

4.  [**名前**] 列の照合順序を変更して、テーブルを保存します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

