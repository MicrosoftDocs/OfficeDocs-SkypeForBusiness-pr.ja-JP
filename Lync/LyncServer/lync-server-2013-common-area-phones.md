---
title: Lync Server 2013 での共通領域電話
TOCTitle: Lync Server 2013 での共通領域電話
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994076(v=OCS.15)
ms:contentKeyID: 52056714
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での共通領域電話

 

_**トピックの最終更新日:** 2016-12-08_

共通領域電話は、個別のユーザーには関連付けられていない IP 電話です。通常、共通領域電話は、個人のオフィスではなく、建物のロビー、カフェテリア、従業員休憩室、ミーティング ルームなど、多くの人々が集まる可能性の高い場所に置かれています。通常、個別のユーザーに割り当てられた音声ポリシーやダイヤル プランを使用して管理される Lync Server の他の電話とは異なり、共通領域電話に個別のユーザーが割り当てられることはありません。つまり、共通領域電話は他の電話と異なる方法で管理する必要があります。

共通領域電話を管理するには、すべての共通領域電話に対して Active Directory ドメイン サービス 連絡先オブジェクトを作成します。このオブジェクトには、ユーザー アカウントのように、ポリシーと音声計画を割り当てることができます。これにより、共通領域電話が個々のユーザーに関連付けられていない場合でも、これらの電話に対する管理機能を保持することができます。

共通領域電話の連絡先オブジェクトの作成、修正および削除方法、展開内の共通領域電話に関する構成情報の構成と表示方法については、このセクションのトピックを参照してください。

> [!NOTE]
> 共通領域電話としては、Aastra 6721ip 共通領域電話、HP 4110 IP 電話、Polycom CX500 IP 共通領域電話を選択できます。Polycom CX3000 IP 会議電話は別の機種の共通領域電話ですが、会議室で使用するためのものです。共通領域電話の詳細については、「<a href="http://technet.microsoft.com/ja-jp/library/gg398958(v=ocs.14).aspx">新型デバイスの選択</a>」の「共通領域電話」のセクション参照してください。


## このセクション中

  - [共通領域電話情報を表示する](lync-server-2013-view-common-area-phone-information.md)

  - [共有エリアの電話の連絡先オブジェクトを作成または変更する](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [ホット デスク機能の有効と無効を切り替える](lync-server-2013-enable-or-disable-hot-desking.md)

  - [共有エリアの電話の連絡先オブジェクトを削除する](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [共有エリアの電話にポリシーを割り当てる](lync-server-2013-assign-policies-to-a-common-area-phone.md)

