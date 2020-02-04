---
title: 'Lync Server 2013: Lync Server ハイブリッド環境を準備および展開する手順'
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
ms.openlocfilehash: 6ebcce8d0021789a409c8f41b5f635d82284b7bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Lync Server 2013 ハイブリッド環境を準備および展開する手順

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-12-08_

次の表に、Skype for Business Online と Microsoft Office 365 でのハイブリッド展開の環境を準備するために必要な手順を示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>完了状態</th>
<th>ステップ</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p>Office 365 のテナントアカウントを作成して、Lync Online を有効にする</p></td>
<td><p>Office <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">365</a>での office 365 と Lync Online について説明します。</p>
<p>環境の Office 365 の準備が整っていることを確認するには、<a href="https://go.microsoft.com/fwlink/p/?linkid=401408">システム要件</a>を参照してください。</p>
<p>Office 365 のセットアップの詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">office 365 の使用を開始</a>する」および「 <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">office 365</a>をセットアップする」を参照してください。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>ドメインを追加して所有権を確認する</p></td>
<td><p>ドメインは、「<em>バニティ ドメイン</em>」とも呼ばれます。Office 365 テナントにドメインを追加して、Office 365 でそのドメインを検証します。この検証は、ドメインの所有者が自分であることを確認するために必要な手順です。</p>
<p>Office 365 テナントにドメインを追加するには、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">office 365 にドメインを追加</a>する」に記載されている手順を実行します。</p>
<p>「Office 365 サービスの DNS レコードを編集する」など&quot;、トピックの各セクションのすべての手順を実行します。&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>環境の準備状況を確認する</p></td>
<td><p>Office 365 セットアップアシスタントを使用して、Office 365 を展開することができます。 詳細については、「<a href="https://go.microsoft.com/fwlink/p/?linkid=254985">セットアップアシスタントを使用して Office 365 の準備を確認する」を</a>参照してください。</p>
<p>このツールの使用と Office 365 の展開の詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">office 365 展開ガイド</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Active Directory の同期を準備する</p></td>
<td><p>Active Directory の同期によって、オンプレミスの Active Directory が Office 365 と継続的に同期されます。 これにより、各ユーザー アカウントおよびグループの同期バージョンを作成できるだけでなく、ローカルの Microsoft Exchange Server 環境から Microsoft Exchange Online へのグローバル アドレス一覧 (GAL) の同期を実行できるようになります。</p>
<div>

> [!IMPORTANT]  
> ユーザーが Lync Online に移行されていない場合でも、組織内のすべての Lync ユーザーの AD アカウントを、オンプレミスとオンラインの Lync 展開の間で同期する必要があります。 すべてのユーザーを同期しない場合、組織のオンプレミス展開のユーザーとオンライン ユーザーとの間の通信が正常に動作しない可能性があります。


</div>
<p>Active Directory 同期のために環境を準備するには、「<a href="https://go.microsoft.com/fwlink/p/?linkid=254988">ディレクトリ同期のロードマップ</a>」で説明されている手順に従ってください。シングルサインオンの設定が含まれます。</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Active Directory フェデレーションサービス (AD FS) 用の証明書を作成する</p></td>
<td><p>Office 365 との id フェデレーションに使用する証明書を作成する必要があります。 詳細については、「<a href="https://go.microsoft.com/fwlink/p/?linkid=285376">チェックリスト: AD fs を使用してシングルサインオンを実装および管理する</a>」の「フェデレーションサーバー証明書の計画と展開」のセクションを参照してください。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>AD FS 用の証明書を割り当てる</p></td>
<td><p>Office 365 との id フェデレーションで使用する証明書を作成したら、それをインストールして割り当てる必要があります。</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>パイロットユーザーを Skype for Business Online に移行する</p></td>
<td><p>Skype for Business Online の環境を準備して構成するための手順を完了したら、パイロットユーザーを Lync Online に移行することができます。</p>
<p>「 <a href="lync-server-2013-move-users-to-lync-online.md">Lync Server 2013 でユーザーを Lync Online に移動する」を</a>参照してください。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>ハイブリッド展開でユーザーを管理する</p></td>
<td><p>ハイブリッド展開でユーザーを管理する方法の詳細については、「<a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">ハイブリッド Lync Server 2013 展開でユーザーを管理</a>する」を参照してください。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

