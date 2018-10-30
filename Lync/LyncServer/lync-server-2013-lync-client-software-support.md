---
title: 'Lync Server 2013: Lync クライアント ソフトウェアのサポート'
TOCTitle: Lync クライアント ソフトウェアのサポート
ms:assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412781(v=OCS.15)
ms:contentKeyID: 48273190
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Lync クライアント ソフトウェアのサポート

 

_**トピックの最終更新日:** 2016-12-08_

このセクションでは、 Lync 2013 と Lync 2013 用オンライン ミーティング アドインのソフトウェア サポートの概要を説明します。

> [!NOTE]
> Outlook メッセージングおよびコラボレーション クライアント内から会議管理をサポートする Lync 2013 用オンライン ミーティング アドインは、Lync 2013 と共に自動的にインストールされます。


### Lync 2013 および Lync 2013 用オンライン ミーティング アドインのソフトウェア要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>システム コンポーネント</th>
<th>最小要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows オペレーティング システム</p></td>
<td><p>Windows 8.1</p>
<p>Windows 8</p>
<p>Windows 7 オペレーティング システム</p>
<p>最新のサービス パックが適用された Windows Server 2008 R2</p>

> [!NOTE]
> Lync 2013 と Lync 2013 用オンライン ミーティング アドイン は、Windows Vista や Windows XP (すべてのバージョン) ではサポートされません。

</div></td>
</tr>
<tr class="even">
<td><p>インストールと更新</p></td>
<td><p>管理者の権限およびアクセス許可</p></td>
</tr>
<tr class="odd">
<td><p>ブラウザー</p></td>
<td><p>Windows Internet Explorer 10 インターネット ブラウザー</p>
<p>Internet Explorer 9 インターネット ブラウザー</p>
<p>Internet Explorer 8 インターネット ブラウザー</p>
<p>Internet Explorer 7 インターネット ブラウザー</p>
<p>Mozilla Firefox Web ブラウザー</p>

> [!NOTE]
> Lync を Microsoft Exchange Onlineと併用し、組織で認証用 HTTP プロキシを展開している場合は、 Internet Explorer 9 または Internet Explorer 8 が必要です。

</div></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Integration</p></td>
<td><p>統合機能の完全なセットの場合:</p>
<ul>
<li><p>Outlook 2013 メッセージングおよびコラボレーション クライアント</p></li>
<li><p>Outlook 2010 メッセージングおよびコラボレーション クライアント</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Microsoft Exchange 統合</p></td>
<td><p>統合機能の完全なセットの場合:</p>
<ul>
<li><p>Microsoft Exchange Server 2013</p></li>
<li><p>Microsoft Exchange Server 2010</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Macintosh オペレーティング システム

Lync 2013 は、Windows のみで使用できます。ただし、Lync Server 2013 では、Mac OS 10.5.8、最新のサービス パック、またはリリース (Intel ベース) のオペレーティング システムを実行しているコンピューターで次のクライアントがサポートされています (Mac OS 10.9 オペレーティング システムは、現在サポートされていません)。サポートされている機能の詳細については、「[Lync Server 2013 のクライアントの比較表](lync-server-2013-desktop-client-comparison-tables.md)」を参照してください。

  - Microsoft Lync for Mac 2011 (「Lync for Mac 2011 展開ガイド」( [http://go.microsoft.com/fwlink/?linkid=268786\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268786%26clcid=0x411)) を参照してください)

  - Microsoft Communicator for Mac 2011 (「Communicator for Mac 2011 展開ガイド」( [http://go.microsoft.com/fwlink/?linkid=268787\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268787%26clcid=0x411)) を参照してください)

## Lync Web App ブラウザー

Lync Web App は、特定の組み合わせのオペレーティング システムとブラウザーをサポートします。詳細については、「計画」のドキュメントの「[Lync Server 2013 の Lync Web App がサポートされるプラットフォーム](lync-server-2013-lync-web-app-supported-platforms.md)」を参照してください。

## Microsoft Office のサポート状況

Lync Server 2013 クライアントは、さまざまなバージョンの Microsoft Office との統合をサポートしています。ここでは、その概要を説明します。

  - Outlook 2013 と Microsoft Outlook 2010 では、Lync 2013 の統合機能がサポートされています。

  - Microsoft Exchange Server 2013 と Microsoft Exchange Server 2010 では、Lync 2013 の統合機能がサポートされています。

  - Office 2013 および Microsoft Office 2010 では、Lync 2013 用オンライン会議アドインがサポートされています。

## 固定プロファイルの使用

ユーザーが Lync 2013 会議機能の使用を予定している場合、ユーザーが Active Directory ドメイン サービス の固定プロファイルを使用して Lync 2013 クライアントにサインインすることを禁止してください。固定プロファイルは読み取り専用のユーザー プロファイルなので、Lync 2013 会議で必要とされる公開キー基板 (PKI) のキーをプロファイルに保存できません。詳細については、Microsoft サポート技術情報の記事 2552221「ユーザーが固定ユーザー プロファイルを使用してサインインしていると Lync 2010 の会議機能が失敗する」( [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x411)) を参照してください。

## 関連項目

#### 概念

[Lync Server 2013 での Lync クライアントのハードウェアのサポート](lync-server-2013-lync-client-hardware-support.md)  
[Lync Server 2013 の Lync クライアント ビデオ要件](lync-server-2013-lync-client-video-requirements.md)  
[Lync Server 2013 で以前の展開からサポートされるクライアント](lync-server-2013-supported-clients-from-previous-deployments.md)

