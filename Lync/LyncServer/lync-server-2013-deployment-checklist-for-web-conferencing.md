---
title: Lync Server 2013 web 会議用の展開チェックリスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5f845fd57846d7f9b58351d1cb77f3f1c0142ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Lync Server 2013 の web 会議の展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-30_

他の Lync Server 2013 コンポーネントの展開と同様に、web 会議の展開では、会議を組み込んだトポロジを作成して公開する必要があります。

<div>

## <a name="deployment-sequence"></a>展開シーケンス

最初のトポロジを展開するとき、または少なくとも1つのフロントエンドプールまたは Standard Edition サーバーを展開した後で、会議を展開することができます。

</div>

<div>

## <a name="conferencing-deployment-process"></a>会議展開プロセス

次の表は、既存のトポロジに会議を展開するために必要な手順の概要を示しています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>段階</th>
<th>手順</th>
<th>役割とグループ メンバーシップ</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><p>会議は、フロントエンドプールと Standard Edition サーバーで、フロントエンドサーバー上で実行されます。 これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。</p>
<div>

> [!NOTE]  
> Lync Server 2013 は、PowerPoint プレゼンテーションの共有とレンダリングを処理するために、Office Web Apps と Office Web Apps サーバーを使用します。 Office Web Apps サーバーのインストールと構成の詳細については、「 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps サーバーおよび Lync server 2013 との統合を構成する</A>」を参照してください。


</div></td>
<td><p>ローカル Administrators グループのメンバーであるドメイン ユーザー</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">サポートされているドキュメントの Lync Server 2013 でサポートされているハードウェア</a></p>
<p>サポートドキュメントの<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート</a></p>
<p>計画ドキュメントの<a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 のシステム要件を決定</a>する。</p>
<p>計画ドキュメントの<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 でのアーカイブの技術要件</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>会議をサポートするために適切な内部トポロジの作成</strong></p></td>
<td><p>トポロジに会議を追加するには、トポロジビルダーを実行して、トポロジを公開します。</p></td>
<td><p>トポロジを定義するには、ローカル Users グループのメンバーであるアカウント</p>
<p>トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであり、Lync Server 2013 ファイルストアで使用されるファイル共有に対するフルコントロールのアクセス許可 (読み取り/書き込み/変更) を持つアカウント (Topology Builder では、必要な Dacl を構成する)</p></td>
<td><p>展開ドキュメントで、「<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">トポロジビルダーでの Lync Server 2013 のトポロジを定義して構成する」</a>を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会議のポリシーとサポートを構成する</strong></p></td>
<td><p>Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、会議の設定を構成します。</p></td>
<td><p>RTCUniversalServerAdmins group (Windows PowerShell のみ) またはユーザーを [] または [CSAdministrator] の役割に割り当てる</p></td>
<td><p>運用ドキュメントの<a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 での会議ポリシー</a> 。</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 には**Maxuploadfilesizemb 枠**の設定が含まれるようになりました。これにより、会議中にアップロードできるファイルのサイズが制限されます。 この設定の既定値は 500 MB です。 **Set-CsConferencingConfiguration**コマンドレットを使用して、 **Maxuploadfilesizemb 飾り枠**を調整できます。

**Maxuploadfilesizemb 枠**は、Lync Web App のファイルアップロード設定を制限していません。 Lync Web App のファイルサイズのアップロードの上限は約30MB に設定されており、IIS の web.config ファイルで制御されます:/Datacollabweb/Int\[\]Lync Web App のファイルサイズのアップロード制限を構成するに`maxRequestLength`は`maxAllowedContentLength` 、以下に示すように、web.config ファイルを使用します。

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

各フロントエンドサーバーの web.config ファイルを更新する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

