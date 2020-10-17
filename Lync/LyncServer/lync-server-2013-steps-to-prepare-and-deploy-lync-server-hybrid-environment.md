---
title: 'Lync Server 2013: Lync Server ハイブリッド環境を準備および展開するための手順'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e7acf5fa315e566094728066bbc798267f029ed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519454"
---
# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Lync Server 2013 ハイブリッド環境を準備および展開するための手順

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-12-08_

次の表に、Skype for Business Online および Microsoft Office 365 を使用したハイブリッド展開用に環境を準備するために必要な手順を示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>完了済み</th>
<th>手順</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p>Office 365 のテナントアカウントを作成して Lync Online を有効にする</p></td>
<td><p>Office 365 および Lync Online ( <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>) について説明します。</p>
<p>環境で Office 365 の準備が整っていることを確認するには、 <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">システム要件</a>を参照してください。</p>
<p>Office 365 のセットアップの詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">365 office を使い始める</a> 」および「 <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">office 365</a>をセットアップする」を参照してください。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>ドメインを追加して所有権を確認する</p></td>
<td><p>ドメインは、 <em>バニティドメイン</em>と呼ばれることもあります。 Office 365 組織にドメインを追加してから、Office 365 でドメインを検証する手順を実行する必要があります。 これは、ドメインの所有者であることを確認するためのものです。</p>
<p>Office 365 組織にドメインを追加するには、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">add your domain To office 365</a>」に記載されている手順に従います。</p>
<p>「 &quot; Office 365 サービスの DNS レコードの編集」を含む、トピックの各セクションのすべての手順を完了します。&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>環境の準備状況を確認する</p></td>
<td><p>Office 365 セットアップアシスタントを使用して、Office 365 を展開することができます。 詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">セットアップアシスタントを使用して Office 365 の準備状況を判断する</a>」を参照してください。</p>
<p>ツールの使用と Office 365 の展開の詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">office 365 展開ガイド</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Active Directory の同期を準備する</p></td>
<td><p>Active Directory 同期では、オンプレミスの Active Directory が Office 365 と継続的に同期されます。 これにより、各ユーザーアカウントおよびグループの同期バージョンを作成できます。また、ローカルの Microsoft Exchange Server 環境から Microsoft Exchange Online へのグローバルアドレス一覧 (GAL) 同期も有効にすることができます。</p>
<div>

> [!IMPORTANT]  
> ユーザーが Lync Online に移動されていない場合でも、組織内のすべての Lync ユーザーの AD アカウントをオンプレミスとオンラインの Lync 展開との間で同期する必要があります。 すべてのユーザーを同期しない場合は、組織内のオンプレミスのユーザーとオンラインユーザーとの間の通信が期待どおりに機能しないことがあります。


</div>
<p>Active Directory 同期のために環境を準備するには、「シングルサインオンの設定」を含む「 <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">ディレクトリ同期のロードマップ</a>」で説明されている手順に従います。</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Active Directory フェデレーションサービス (AD FS) の証明書を作成する</p></td>
<td><p>Office 365 との id フェデレーションで使用される証明書を作成する必要があります。 詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">チェックリスト: AD fs を使用してシングルサインオンを実装および管理する</a>」の「ad Fs を計画して展開する」の「フェデレーションサーバー証明書」セクションを参照してください。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>AD FS 用の証明書の割り当て</p></td>
<td><p>Office 365 との id フェデレーションで使用される証明書を作成した後、それらをインストールして割り当てる必要があります。</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>パイロットユーザーを Skype for Business Online に移動する</p></td>
<td><p>Skype for Business Online の環境を準備および構成する手順を完了したら、パイロットユーザーの Lync Online への移行を開始できます。</p>
<p>「 <a href="lync-server-2013-move-users-to-lync-online.md">Lync Server 2013 でユーザーを Lync Online に移行する」を</a>参照してください。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>ハイブリッド展開でユーザーを管理する</p></td>
<td><p>ハイブリッド展開でユーザーを管理する方法の詳細については、「 <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">ハイブリッド Lync Server 2013 展開でユーザー</a>を管理する」を参照してください。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

