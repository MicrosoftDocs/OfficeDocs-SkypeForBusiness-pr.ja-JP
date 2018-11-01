---
title: Web 会議の展開チェックリスト
TOCTitle: Web 会議の展開チェックリスト
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48272975
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Web 会議の展開チェックリスト

 

_**トピックの最終更新日:** 2015-03-09_

他の Lync Server 2013 コンポーネントの場合と同様に、Web 会議を展開する場合もトポロジ ビルダーを使用して、会議が組み込まれるトポロジを作成して公開する必要があります。

## 展開順序

Web 会議は、最初のトポロジを展開するのと同時に展開するか、または少なくとも 1 つのフロント エンド プールまたは Standard Edition サーバーを展開した後で展開できます。

## 電話会議展開プロセス

次の表に、既存のトポロジに電話会議を展開するために必要なステップの概要を示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>フェーズ</th>
<th>ステップ</th>
<th>役割とグループ メンバーシップ</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><p>Web 会議は、フロント エンド プールと Standard Edition サーバーのフロント エンド サーバーで実行されます。これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。</p>

> [!NOTE]
> Lync Server 2013 では、Office Web Apps と Office Web Apps サーバー を使用して、PowerPoint プレゼンテーションの共有とレンダリングを処理します。Office Web Apps サーバー のインストールと構成については、「<a href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Lync Server 2013 と Office Web Apps サーバーの統合の構成</a>」を参照してください。

</div></td>
<td><p>ローカルの Administrators グループのメンバーであるドメイン ユーザー</p></td>
<td><p>「サポート」のドキュメントの「<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 でサポートされるハードウェア</a>」。</p>
<p>「サポート」のドキュメントの「<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 でのサーバーのソフトウェアおよびインフラストラクチャ サポート</a>」。</p>
<p>「計画」のドキュメントの「<a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 システム要件の決定</a>」。</p>
<p>「計画」のドキュメントの「<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 のアーカイブの技術要件</a>」。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>電話会議をサポートするために適切な内部トポロジの作成</strong></p></td>
<td><p>トポロジ ビルダーを実行して、Web 会議をトポロジに追加した後、そのトポロジを公開します。</p></td>
<td><p>トポロジを定義するには、ローカル ユーザー グループのメンバーであるアカウント</p>
<p>トポロジを公開するには、Domain Admins グループと RTCUniversalServerAdmins グループのメンバーであり、Lync Server 2013 ファイル ストアに使用するファイル共有のフル コントロールのアクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジ ビルダーが必要な DACL を構成できるようにするため)</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Lync Server 2013 のトポロジ ビルダーでのトポロジの定義と構成</a>」。</p></td>
</tr>
<tr class="odd">
<td><p><strong>電話会議ポリシーとサポートの構成</strong></p></td>
<td><p>Lync Server 2013 コントロール パネルまたは Lync Server 管理シェルを使用して、会議設定を構成します。</p></td>
<td><p>RTCUniversalServerAdmins グループ (Windows PowerShell のみ) あるいは [] または CSAdministrator の役割にユーザーを割り当てます。</p></td>
<td><p>「操作」のドキュメントの「<a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 での会議ポリシー</a>」。</p></td>
</tr>
</tbody>
</table>


現在、Lync Server 2013 には、**MaxUploadFileSizeMb** の設定が含まれています。これは、会議中にアップロード可能なファイルのサイズを制限します。この設定の既定値は 500 MB です。**Set-CsConferencingConfiguration** コマンドレットを使用すると、**MaxUploadFileSizeMb** を調整できます。

**MaxUploadFileSizeMb** では、Lync Web App のファイルのアップロードの設定が制限されません。Lync Web App のファイルのアップロード サイズの制限は約 30 MB に設定され、IIS の web.config ファイル (/DataCollabWeb/Int\[Ext\]/Handler/web.config) によって制御されます。Lync Web App のファイルのアップロード サイズの制限を構成するには、以下のように、web.config ファイルで `maxRequestLength` および `maxAllowedContentLength` を更新してください。

    <system.web>
        <!-- Since this handler is used to upload files to DMCU the request size (in kilobytes) 
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

web.config ファイルはフロント エンド サーバーごとに更新する必要があります。

