---
title: 'Lync Server 2013: Lync Server ハイブリッド環境を準備および展開する手順'
TOCTitle: Lync Server 2013 ハイブリッド環境を準備および展開する手順
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48273175
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 ハイブリッド環境を準備および展開する手順

 

_**トピックの最終更新日:** 2016-12-08_

次の表に、Microsoft Lync Online および Microsoft Office 365 とのハイブリッド展開を実現する環境の準備に必要な手順を示します。


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
<td><p></p></td>
<td><p>Office 365 および有効な Lync Online のテナント アカウントを作成する</p></td>
<td><p>Office 365 および Lync Online の詳細については、「<a href="http://go.microsoft.com/fwlink/?linkid=254980">Office 365</a>」を参照してください。</p>
<p>ご使用の環境で Office 365 を使用する準備ができていることを確認するには、「<a href="http://go.microsoft.com/fwlink/p/?linkid=401408">システム要件</a>」を参照してください。</p>
<p>Office 365 のセットアップの詳細については、「<a href="http://go.microsoft.com/fwlink/?linkid=254982">Office 365 の使用を開始</a>」および「<a href="http://go.microsoft.com/fwlink/?linkid=254979">Office 365 をセットアップする</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>ドメインを追加して所有権を確認する</p></td>
<td><p>ドメインは、「<em>バニティ ドメイン</em> 」とも呼ばれます。Office 365 テナントにドメインを追加して、Office 365 でそのドメインを検証します。この検証は、ドメインの所有者が自分であることを確認するために必要な手順です。</p>
<p>Office 365 テナントにドメインを追加するには、「<a href="http://go.microsoft.com/fwlink/?linkid=254983">Office 365 にドメインを追加する</a>」に記載されている手順に従ってください。</p>
<p>「Office 365 サービスの DNS レコードを編集する」を含む、トピックの各セクションのすべての手順を完了してください。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>環境を準備できたことを確認する</p></td>
<td><p>Office 365 セットアップ アシスタントを使用すると、Office 365 を簡単に展開できます。詳細については、「<a href="http://go.microsoft.com/fwlink/p/?linkid=254985">Microsoft Office 365 Deployment Readiness Tool / OnRamp for Office 365</a>」を参照してください。</p>
<p>ツールの使用法および Office 365 の展開方法については、「<a href="http://go.microsoft.com/fwlink/p/?linkid=257337">エンタープライズ向け Microsoft Office 365 展開ガイド (Microsoft Office 365 Deployment Guide for Enterprises)</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Active Directory の同期を準備する</p></td>
<td><p>Active Directory 同期は、社内の Active Directory を、常に Office 365 と同期した状態に保ちます。これにより、各ユーザー アカウントおよびグループの同期バージョンを作成できるだけでなく、ローカルの Microsoft Exchange Server 環境から Microsoft Exchange Online へのグローバル アドレス一覧 (GAL) の同期を実行できるようになります。</p>
<div>

> [!IMPORTANT]
> ユーザーが Lync Online に移動されない場合でも、組織のすべての Lync ユーザーの AD アカウントを内部設置型 Lync 展開とオンライン Lync 展開との間で同期する必要があります。すべてのユーザーを同期しない場合、組織の内部設置型展開のユーザーとオンライン ユーザーとの間の通信が正常に動作しない可能性があります。


</div>
<p>Active Directory 同期のために環境を準備するには、「<a href="http://go.microsoft.com/fwlink/p/?linkid=254988">Active Directory 同期: ロードマップ</a>」に記載されている手順に従ってください。この手順には、シングル サインオンのセットアップが含まれます。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Active Directory フェデレーション サービス (AD FS) 用の資格情報を作成する</p></td>
<td><p>Office 365 との ID フェデレーションで使用する資格情報を作成する必要があります。詳細については、「<a href="http://go.microsoft.com/fwlink/p/?linkid=285376">チェックリスト: AD FS によるシングル サインオンを実装して管理する</a>」の「シングル サインオンで使用するために AD FS を計画して展開する (Plan for and deploy AD FS for use with single sign-on)」の「フェデレーション サーバーの証明書 (Federation server certificates)」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>AD FS 用の証明書を割り当てる</p></td>
<td><p>Office 365 との ID フェデレーションで使用される証明書を作成した後は、それらをインストールして割り当てる必要があります。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>パイロット ユーザーを Skype for Business Online に移動する</p></td>
<td><p>Skype for Business Online 用に環境を準備および構成する手順が完了したら、Lync Online へのパイロット ユーザーの移行を開始できます。</p>
<p>「<a href="lync-server-2013-move-users-to-lync-online.md">Lync Server 2013 でユーザーを Lync Online に移動する</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>ハイブリッド展開でユーザーを管理する</p></td>
<td><p>ハイブリッド展開でユーザーを管理する方法の詳細については、「<a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">ハイブリッド Lync Server 2013 展開でユーザーを管理する</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>

