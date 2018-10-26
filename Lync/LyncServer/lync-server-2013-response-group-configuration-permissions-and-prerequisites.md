---
title: 'Lync Server 2013: 応答グループ構成のアクセス許可と前提条件'
TOCTitle: 応答グループ構成のアクセス許可と前提条件
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48271903
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の応答グループ構成のアクセス許可と前提条件

 

_**トピックの最終更新日:** 2016-12-08_

応答グループは エンタープライズ VoIP 通話管理機能です。このトピックでは、応答グループ を構成する前に準備する必要のある事項、および構成タスクの実行に必要な管理者資格情報とアクセス許可について説明します。

このセクションでは、応答グループに関連する「計画」のドキュメントを読んでいることが前提となります。詳細については、「計画」のドキュメントの「[Lync Server 2013 通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照してください。

## 構成ツールと管理役割

次の管理ツールを使用して 応答グループを構成できます。

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
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
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
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
<td><p>チェック</p></td>
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


> [!NOTE]
> <strong>(1)</strong> Active Directory ドメイン サービス のユーザー オブジェクトは、この表に掲載された指定の Active Directory セキュリティ グループのメンバーである必要があります。管理者、またはユーザーをセキュリティ グループに追加するための適切なアクセス許可を持つその他の委任された Active Directory グループ メンバー (Administrator、Account Operators など) は、掲載されたセキュリティ グループ、または掲載された機能をユーザーが実行できるグループにユーザー オブジェクトを追加する必要があります。<strong>(2)</strong> CsResponseGroupAdministrator が CsResponseGroupManager に割り当てたワークフローのみ。<strong>(3)</strong> 応答グループ マネージャーは、CsResponseGroupManager の他のメンバーを、現在のマネージャーが既に管理しているワークフローに割り当てることができます。<strong>(4)</strong> CsViewOnlyAdministrator は、動詞 &quot;Get&quot; の Lync Server 管理シェル コマンドレットのみを実行できます。


## 応答グループ構成の前提条件

応答グループでは、次のコンポーネントが必要です。

  - アプリケーション サービス

  - 応答グループ アプリケーション

  - 言語パック

  - ファイル ストア (オーディオ ファイルを格納)

  - Web サービス (応答グループ構成ツール、エージェントのサインインおよびサインアウト コンソールを含む)

これらのコンポーネントはすべて、エンタープライズ VoIP を展開するときに既定でインストールされます。

応答グループを構成する前に次のタスクを実行しなければならない場合があります。

  - Lync Server 2013 および エンタープライズ VoIP に対してユーザーを有効化します。

  - Federal Information Processing Standards (FIPS) に準拠するように構成ファイルを変更します。

  - キュー名やエージェント グループ名で Yi、Meng、および Zang の文字がサポートされるようにデータベースの照合順序を変更します。

## ユーザーの有効化

応答グループの構成で行う最初のステップはエージェント グループの作成です。エージェント グループを作成する前に、Lync Server 2013 および エンタープライズ VoIP の 応答グループのエージェントとなるユーザーを有効化する必要があります。Lync Server 2013 に対するユーザーの有効化は、通常、Enterprise Edition サーバーまたは Standard Edition サーバーの展開時に行います。ユーザーを Lync Server 2013 に対して有効にする方法については、「[Lync Server 2013 ユーザー アカウントの再有効化または無効化](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)」を参照してください。エンタープライズ VoIP に対するユーザーの有効化は、通常、エンタープライズ VoIP の展開時に行います。詳細については、「[Lync Server 2013 でのエンタープライズ VoIP に対するユーザーの有効化](lync-server-2013-enable-users-for-enterprise-voice.md)」を参照してください。

## FIPS 要件の準拠

このセクションは、組織が FIPS (Federal Information Processing Standards) に準拠する必要がある場合にのみ参照してください。

FIPS に準拠するには、Web サービスのインストール後、異なる暗号化アルゴリズムを使用するようにアプリケーション レベルの Web.config ファイルを変更する必要があります。ASP.NET が 3DES (Triple Data Encryption Standard) アルゴリズムを使用してビュー状態データを処理するように指定する必要があります。応答グループ アプリケーションの場合、この要件は 応答グループ構成ツールおよびエージェントのサインイン/サインアウト コンソールに適用されます。この要件の詳細については、マイクロソフト サポート技術情報の記事 911722「ASP にアクセスすると、エラー メッセージを受け取ることがあります。ASP からのアップグレード後に有効に ViewState を持つ NET Web ページ。Asp NET 1.1 説明します。NET 2.0」([http://go.microsoft.com/fwlink/?linkid=196183\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=196183%26clcid=0x411)) を参照してください。

Web.config ファイルを変更するには、以下の手順を実行します。

1.  メモ帳などのテキスト エディターで、アプリケーションレベルの Web.config ファイルを開きます。

2.  Web.config ファイルで `<system.web>` セクションを見つけます。

3.  次の `<machineKey>` セクションを `<system.web>` セクション内に追加します。
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Web.config ファイルを保存します。

5.  コマンド プロンプトで次のコマンドを実行して、インターネット インフォメーション サービス (IIS) サービスを再起動します。
    
        iisreset

## Yi、Meng、および Zang の文字のサポート

このセクションは、組織で Yi、Meng、または Zang の文字をサポートする必要がある場合に参照してください。

> [!NOTE]
> Yi、Meng、および Zang 文字の詳細、およびこれらの文字が展開において重要となる理由については、GB18030 文字セットについての情報 (<a href="http://go.microsoft.com/fwlink/?linkid=240223%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=240223&amp;clcid=0x411</a>) を参照してください。


Yi、Meng、または Zang の文字をサポートするには、Rgsconfig データベースの照合順序を変更する必要があります。 各 Rgsconfig データベースの以下の表にある \[**名前**\] 列の照合順序を変更します。

  - dbo.AgentGroups

  - dbo.BusinessHours

  - dbo.HolidaySets

  - dbo.Queues

  - dbo.Workflows

SQL Server 2008 R2 および SQL Server 2012 については、Latin\_General\_100 (アクセントを区別する) 照合順序を使用してください。この照合順序を使用する場合は、どのオブジェクト名も大文字と小文字は区別されません。

照合順序は、Microsoft SQL Server Management Studio を使用して変更できます。このツールの使用の詳細については、「SQL Server Management Studio の使用」([http://go.microsoft.com/fwlink/?linkid=196184\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=196184%26clcid=0x411)) を参照してください。照合順序を変更するには、以下の手順に従います。

1.  表の再作成を必要とする変更が SQL Server Management Studio で許可されていることを確認します。詳細については、「\[保存 (許可されない)\] ダイアログ ボックス」([http://go.microsoft.com/fwlink/?linkid=196186\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=196186%26clcid=0x411)) を参照してください。列の照合順序の設定については、「列の照合順序を設定する方法 (Visual Database Tools)」([http://go.microsoft.com/fwlink/?linkid=196185\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=196185%26clcid=0x411)) を参照してください。

2.  Microsoft SQL Server Management Studio を使用して、Rgsconfig データベースに接続します。

3.  Rgsconfig データベースで変更したい表を見つけて右クリックし、\[**設計**\] をクリックします。

4.  \[**名前**\] 列の照合順序を変更して、表を保存します。

