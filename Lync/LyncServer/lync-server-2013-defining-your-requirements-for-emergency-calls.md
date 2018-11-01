---
title: 'Lync Server 2013: 緊急電話の要件の定義'
TOCTitle: 緊急電話の要件の定義
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48272206
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での緊急電話の要件の定義

 

_**トピックの最終更新日:** 2015-03-09_

Microsoft Lync Server 2013 の E9-1-1 展開を開始する前に、以下のセクションに記載されている質問に答えることができるようにしておく必要があります。必要な計画は、展開する E9-1-1 ソリューションの種類 (SIP トランク E9-1-1 サービス プロバイダー、または緊急位置識別番号 (ELIN) ゲートウェイ) によって異なります。 次の表は、この計画ブックで確認する必要があるセクションをソリューションの種類別に示しています。

### E9-1-1 ソリューションの種類別の計画手順

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>SIP トランク サービス プロバイダー</th>
<th>ELIN ゲートウェイ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013 での E9-1-1 展開の範囲の定義</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013 での E9-1-1 展開の範囲の定義</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Lync Server 2013 での場所の判断に使用するネットワーク要素の定義</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Lync Server 2013 での場所の判断に使用するネットワーク要素の定義</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Lync Server 2013 で、E9-1-1 でユーザーを有効にする</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Lync Server 2013 で、E9-1-1 でユーザーを有効にする</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Lync Server 2013 での SIP トランク サービス プロバイダーの場所の管理</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Lync Server 2013 での ELIN ゲートウェイの場所の管理</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Lync Server 2013 での手動で場所を取得する際のユーザー エクスペリエンスの定義</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Lync Server 2013 での手動で場所を取得する際のユーザー エクスペリエンスの定義</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Lync Server 2013 での E9-1-1 の SIP トランクの設計</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013 でのセキュリティ デスクの追加</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013 でのセキュリティ デスクの追加</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Lync Server 2013 の場所ポリシーの定義</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Lync Server 2013 の E9-1-1 サービス プロバイダーの選択</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Lync Server 2013 での場所ポリシーのスコープの割り当て</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Lync Server 2013 の場所ポリシーの定義</a></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Lync Server 2013 での場所ポリシーのスコープの割り当て</a></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## このセクション中

  - [Lync Server 2013 での E9-1-1 展開の範囲の定義](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [Lync Server 2013 での場所の判断に使用するネットワーク要素の定義](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [Lync Server 2013 で、E9-1-1 でユーザーを有効にする](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [Lync Server 2013 での SIP トランク サービス プロバイダーの場所の管理](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [Lync Server 2013 での ELIN ゲートウェイの場所の管理](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [Lync Server 2013 での手動で場所を取得する際のユーザー エクスペリエンスの定義](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [Lync Server 2013 での E9-1-1 の SIP トランクの設計](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [Lync Server 2013 でのセキュリティ デスクの追加](lync-server-2013-including-the-security-desk.md)

  - [Lync Server 2013 の E9-1-1 サービス プロバイダーの選択](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [Lync Server 2013 の場所ポリシーの定義](lync-server-2013-defining-the-location-policy.md)

  - [Lync Server 2013 での場所ポリシーのスコープの割り当て](lync-server-2013-assigning-location-policy-scope.md)

