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
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="15c54-105">Skype for Business 会議に接続されているサイズの大きなファイルを保持</span><span class="sxs-lookup"><span data-stu-id="15c54-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="15c54-p102">Skype for Business 会議をする参加者を選択し、開いているが、[ダウンロードするファイルを添付することができます。メールボックスの訴訟保持上に配置を Office 365 のアイテム保持ポリシーを適用したり、Office 365 のセキュリティには、電子情報開示ケースに関連付けられている保留にすべての参加者のメールボックスで Skype for Business 会議の添付ファイルが保存されます。&amp;コンプライアンス センターします。このコンテンツは、自分のメールボックス内の参加者の**回復できるアイテム**フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="15c54-p102">You can attach files to a Skype for Business meeting, which participants can then open and download. Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center. This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="15c54-p103">保留中のメールボックスに保持されているファイルはインデックスが、セキュリティでコンテンツ検索の実行時にしたがって検索できる&amp;コンプライアンス センター参加者のメールボックスを検索します。ただし、39 MB を超えている添付ファイルは、2 つ以上の小さなファイルに分割し、圧縮 (.zip) ファイルとして保存します。これらの小さいファイルの*コンテンツ*の検索] いないインデックスが作成されコンテンツ検索では返されません可能性があります。ただし、これらのファイル (ファイル名と作成者) などの*メタデータ*は、検索用インデックスが、コンテンツの検索で返される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="15c54-p103">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox. However, attached files that are larger than 39 MB are split into two or more smaller files and saved as compressed (.zip) files. The  *content*  of these smaller files is not indexed for search, and might not be returned in a Content Search. However, the *metadata*  of these files (such as the file name and author) is indexed for search, and might be returned in a Content Search.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15c54-p104">メールボックスがいっぱいまたは MaxSendSize 39 MB よりも小さくなるように構成テナント管理者の場合は、ファイルのすべてのデータは保持されませんをアップロードします。既定の MaxSendSize は 150 MB、ですが、テナント管理者が 1 MB とサイズを小さくする MaxSendSize を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="15c54-p104">If the mailbox is full or the tenant admin has configured MaxSendSize to be smaller than 39 MB, uploaded file data will not be retained at all. The default MaxSendSize is 150 MB, but tenant admins can configure MaxSendSize to be as small as 1 MB.</span></span> 
  
<span data-ttu-id="15c54-p105">保留リストに含まれていないメールボックスでは、保存されているすべての会議データはありません。たとえばの 3 つの会議で、これら 2 つの参加者のメールボックスに会議のデータが保存されているは、3 番目の参加者のメールボックスにメールボックスではありませんでの 2 つの参加者のメールボックスが保持マークが付いているままにします。</span><span class="sxs-lookup"><span data-stu-id="15c54-p105">Mailboxes that are not on hold will not have any meeting data saved. For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="15c54-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="15c54-117">Related topics</span></span>
[<span data-ttu-id="15c54-118">ユーザー設定の外部アクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="15c54-118">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="15c54-119">ブロック ポイント間接ファイル転送</span><span class="sxs-lookup"><span data-stu-id="15c54-119">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="15c54-120">組織のクライアントのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="15c54-120">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="15c54-121">組織内の会議のポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="15c54-121">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  