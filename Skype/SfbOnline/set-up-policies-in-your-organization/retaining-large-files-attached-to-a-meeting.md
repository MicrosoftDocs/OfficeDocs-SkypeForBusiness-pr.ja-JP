---
title: "Skype for Business 会議に接続されているサイズの大きなファイルを保持"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Skype for Business 会議をする参加者を選択し、開いているが、[ダウンロードするファイルを添付することができます。メールボックスの訴訟保持上に配置を Office 365 のアイテム保持ポリシーを適用したり、Office 365 のセキュリティには、電子情報開示ケースに関連付けられている保留にすべての参加者のメールボックスで Skype for Business 会議の添付ファイルが保存されます。&amp;コンプライアンス センターします。このコンテンツは、自分のメールボックス内の参加者の回復できるアイテム フォルダーに保存されます。"
ms.openlocfilehash: 59e1470d36aac988b1e0ff6ee40ebc1fb61967ed
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Skype for Business 会議に接続されているサイズの大きなファイルを保持

Skype for Business 会議をする参加者を選択し、開いているが、[ダウンロードするファイルを添付することができます。メールボックスの訴訟保持上に配置を Office 365 のアイテム保持ポリシーを適用したり、Office 365 のセキュリティには、電子情報開示ケースに関連付けられている保留にすべての参加者のメールボックスで Skype for Business 会議の添付ファイルが保存されます。&amp;コンプライアンス センターします。このコンテンツは、自分のメールボックス内の参加者の**回復できるアイテム**フォルダーに保存されます。
  
保留中のメールボックスに保持されているファイルはインデックスが、セキュリティでコンテンツ検索の実行時にしたがって検索できる&amp;コンプライアンス センター参加者のメールボックスを検索します。ただし、39 MB を超えている添付ファイルは、2 つ以上の小さなファイルに分割し、圧縮 (.zip) ファイルとして保存します。これらの小さいファイルの*コンテンツ*の検索] いないインデックスが作成されコンテンツ検索では返されません可能性があります。ただし、これらのファイル (ファイル名と作成者) などの*メタデータ*は、検索用インデックスが、コンテンツの検索で返される可能性があります。
  
> [!NOTE]
> メールボックスがいっぱいまたは MaxSendSize 39 MB よりも小さくなるように構成テナント管理者の場合は、ファイルのすべてのデータは保持されませんをアップロードします。既定の MaxSendSize は 150 MB、ですが、テナント管理者が 1 MB とサイズを小さくする MaxSendSize を構成することができます。 
  
保留リストに含まれていないメールボックスでは、保存されているすべての会議データはありません。たとえばの 3 つの会議で、これら 2 つの参加者のメールボックスに会議のデータが保存されているは、3 番目の参加者のメールボックスにメールボックスではありませんでの 2 つの参加者のメールボックスが保持マークが付いているままにします。
  
## <a name="related-topics"></a>関連トピック
[ユーザー設定の外部アクセス ポリシーを作成します。](create-custom-external-access-policies.md)

[ブロック ポイント間接ファイル転送](block-point-to-point-file-transfers.md)

[組織のクライアントのポリシーを設定します。](set-up-client-policies-for-your-organization.md)

[組織内の会議のポリシーを設定します。](set-up-conferencing-policies-for-your-organization.md)
  