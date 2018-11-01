---
title: 'Lync Server 2013: アナウンス アプリケーションの展開プロセス'
TOCTitle: アナウンス アプリケーションの展開プロセス
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48272449
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のアナウンス アプリケーションの展開プロセス

 

_**トピックの最終更新日:** 2015-03-09_

このセクションでは、アナウンス アプリケーションの展開に含まれるステップの概要を説明します。アナウンスを構成する前に、エンタープライズ VoIP を展開する必要があります。アナウンス アプリケーションで必要なコンポーネントは、エンタープライズ VoIP の展開時にインストールされ、有効にされます。

### アナウンスの展開プロセス

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
<th>役割</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アナウンス設定の構成</p></td>
<td><ul>
<li><p>オーディオ ファイルをレコーディングして読み込むか、音声合成 (TTS) を使用して、アナウンスを作成します。</p></li>
<li><p>割り当てられていない番号の表で、割り当てられていない番号の範囲を構成して、適切なアナウンスに関連付けます。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">Lync Server 2013 でのアナウンスの作成</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Lync Server 2013 での割り当てられていない番号の表の構成</a></p></td>
</tr>
<tr class="even">
<td><p>アナウンスの展開の確認</p></td>
<td><p>アナウンスを聞いてテストし、構成が予想どおりに動作することを確認します。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">(オプション) Lync Server 2013 でのアナウンスの展開の確認</a></p></td>
</tr>
</tbody>
</table>

