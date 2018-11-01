---
title: 場所データベースの構成
TOCTitle: 場所データベースの構成
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48272714
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 場所データベースの構成

 

_**トピックの最終更新日:** 2012-09-17_

クライアントがネットワーク内の各自の場所を自動検出できるようにするには、まず場所データベースを構成する必要があります。場所データベースを構成しておらず、場所のポリシーで \[**場所は必須**\] が \[**はい**\] または \[**免責事項**\] に設定されている場合、ユーザーは場所を手動で入力するよう求められます。

場所データベースを構成するには、次のタスクを実行します。

1.  ネットワーク要素と場所のマッピングをデータベースに設定します。緊急位置識別番号 (ELIN) ゲートウェイを使用している場合は、ELIN を \<CompanyName\> フィールドに含める必要があります。

2.  E9-1-1 サービス プロバイダーで保持されている主要道路住所案内 (MSAG) と照らし合わせて住所を確認します。

3.  更新したデータベースを公開します。

> [!NOTE]
> または、場所データベースの代わりに使用できるセカンダリ場所データベースを定義することもできます。詳細については、「<a href="lync-server-2013-configure-a-secondary-location-information-service.md">セカンダリ場所情報サービスの構成</a>」を参照してください。


## このセクション中

  - [場所データベースの設定](lync-server-2013-populate-the-location-database.md)

  - [住所の確認](lync-server-2013-validate-addresses.md)

  - [場所データベースの公開](lync-server-2013-publish-the-location-database.md)

