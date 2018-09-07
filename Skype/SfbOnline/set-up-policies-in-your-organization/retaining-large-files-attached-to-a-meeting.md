---
title: ビジネス会議のため、Skype に接続されている大容量のファイルを保持します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Skype ビジネス会議、どの参加者を選択し、開いてできますし、ダウンロードのためにファイルを添付することができます。 Skype ビジネス会議のための添付ファイルはメールボックスを持つ証拠保全に、Office 365 リテンション ・ ポリシーが適用される、または Office 365 のセキュリティ、電子的証拠開示のケースに関連付けられている保留リストに配置されます。 任意の参加者のメールボックスに保持されます。&amp;コンプライアンス センターです。 このコンテンツは、自分のメールボックス内の参加者の回復可能なアイテム フォルダーに保存されます。
ms.openlocfilehash: b38f2ec56fb53932c08ede2a8c6f39557216a6b8
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864977"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>ビジネス会議のため、Skype に接続されている大容量のファイルを保持します。

Skype ビジネス会議、どの参加者を選択し、開いてできますし、ダウンロードのためにファイルを添付することができます。 Skype ビジネス会議のための添付ファイルはメールボックスを持つ証拠保全に、Office 365 リテンション ・ ポリシーが適用される、または Office 365 のセキュリティ、電子的証拠開示のケースに関連付けられている保留リストに配置されます。 任意の参加者のメールボックスに保持されます。&amp;コンプライアンス センターです。 このコンテンツは、自分のメールボックス内の参加者の**回復可能なアイテム**フォルダーに保存されます。
  
保留中のメールボックスに保持されるファイルはインデックスが、セキュリティ コンテンツの検索を実行している場合、したがって検索できる&amp;コンプライアンス センターの関係者のメールボックスを検索する場合。 ただし、39 MB より大きい添付ファイルは 2 つ以上のサイズの小さいファイルに分割するには、圧縮 (.zip) ファイルとして保存します。 これらの小さいファイルの*コンテンツ*は、検索、インデックス付けされていないと、コンテンツ検索では返されない可能性があります。 ただし、これらのファイル (ファイル名や作成者) などの*メタデータ*検索、インデックスが作成され、コンテンツの検索で返される可能性があります。
  
> [!NOTE]
> メールボックスがいっぱいか、テナント管理者には、39 MB より小さくなるように MaxSendSize が構成されている場合は、ファイルのすべてのデータは保持されませんをアップロードします。 MaxSendSize の既定値は 150 MB ですが、テナント管理者は、サイズは 1 MB に MaxSendSize を構成できます。 
  
保留リストに記載されていないメールボックスは、会議データを保存を必要はありません。 などの 3 つの会議の参加者の 2 つのメールボックスが保持マークが付いている、会議データは、これら 2 つの参加者のメールボックスに保存されますが、3 つ目の参加者のメールボックスにメールボックスを持つではありませんを保持します。
  
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ブロック ポイント ツー ポイントのファイルの転送](block-point-to-point-file-transfers.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織内の会議ポリシーを設定します](set-up-conferencing-policies-for-your-organization.md)
  
  
 