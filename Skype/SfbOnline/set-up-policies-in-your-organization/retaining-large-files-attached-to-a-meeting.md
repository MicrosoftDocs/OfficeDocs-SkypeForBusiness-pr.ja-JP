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
ms.openlocfilehash: e72a5e5ffa47ef3e451f4f4830e8cd6c524d70a7
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "25436638"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="e0f27-105">ビジネス会議のため、Skype に接続されている大容量のファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="e0f27-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="e0f27-106">Skype ビジネス会議、どの参加者を選択し、開いてできますし、ダウンロードのためにファイルを添付することができます。</span><span class="sxs-lookup"><span data-stu-id="e0f27-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="e0f27-107">Skype ビジネス会議のための添付ファイルはメールボックスを持つ証拠保全に、Office 365 リテンション ・ ポリシーが適用される、または Office 365 のセキュリティ、電子的証拠開示のケースに関連付けられている保留リストに配置されます。 任意の参加者のメールボックスに保持されます。&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="e0f27-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="e0f27-108">このコンテンツは、自分のメールボックス内の参加者の**回復可能なアイテム**フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e0f27-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="e0f27-109">保留中のメールボックスに保持されるファイルはインデックスが、セキュリティ コンテンツの検索を実行している場合、したがって検索できる&amp;コンプライアンス センターの関係者のメールボックスを検索する場合。</span><span class="sxs-lookup"><span data-stu-id="e0f27-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="e0f27-110">ただし、30 MB より大きい添付ファイルは 2 つ以上のサイズの小さいファイルに分割するには、圧縮 (.zip) ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="e0f27-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="e0f27-111">これらの小さいファイルの*コンテンツ*は、検索用インデックス付けされていないと、コンテンツ検索では返されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0f27-111">The  *content*  of these smaller files is not indexed for search and might not be returned in a Content Search.</span></span> <span data-ttu-id="e0f27-112">ただし、これらのファイル (ファイル名や作成者) などの*メタデータ*は、検索用インデックスが作成されて、コンテンツの検索で返される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0f27-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search and might be returned in a Content Search.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e0f27-113">Skype からビジネス会議のための大規模なファイルを保持する機能、MaxReceiveSize と MaxSendSize の設定、Exchange Online のメールボックスに影響します。</span><span class="sxs-lookup"><span data-stu-id="e0f27-113">The MaxReceiveSize and MaxSendSize settings for an Exchange Online mailbox can affect the ability to retain large files from Skype for Business meetings.</span></span> <span data-ttu-id="e0f27-114">MaxReceiveSize と MaxSendSize の既定の設定は、それぞれ 36 MB と、35 MB です。</span><span class="sxs-lookup"><span data-stu-id="e0f27-114">The default settings for MaxReceiveSize and MaxSendSize are 36 MB and 35 MB, respectively.</span></span> <span data-ttu-id="e0f27-115">ただし、これらの既定の設定は、30 MB より大きいビジネス会議のため、Skype から任意のファイルを保持するには小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="e0f27-115">However, these default settings are too small to retain any file from a Skype for Business meeting that's larger than 30 MB.</span></span> <span data-ttu-id="e0f27-116">23 MB は保持されませんより大きいファイルを実際には、接続されています。</span><span class="sxs-lookup"><span data-stu-id="e0f27-116">In fact, attached files larger than 23 MB will not be retained.</span></span> <span data-ttu-id="e0f27-117">Exchange オンラインのメッセージの添付ファイルとその他のバイナリ データは Base64 エンコードを使用するためです。</span><span class="sxs-lookup"><span data-stu-id="e0f27-117">This is because Exchange Online uses Base64 encoding of message attachments and other binary data.</span></span> <span data-ttu-id="e0f27-118">メッセージをエンコードすると、そのサイズは約 33% 増加します。</span><span class="sxs-lookup"><span data-stu-id="e0f27-118">When a message is encoded, its size is increased by approximately 33%.</span></span> <span data-ttu-id="e0f27-119">したがって、Skype のビジネス ・ ミーティング用の大きなファイルを保存することを確認するには、お勧め MaxReceiveSize と MaxSendSize 39 MB (約 33%、30 MB サイズの上限値については、以前よりも大きい) には、両方の値を大きくことユーザーを保留リストに配置されます。</span><span class="sxs-lookup"><span data-stu-id="e0f27-119">Therefore, to ensure that large files from Skype for Business meetings are retained, we recommend that you increase the value for both MaxReceiveSize and MaxSendSize to 39 MB (which is approximately 33% larger than the 30 MB size limit that was previously explained) for users who are placed on hold.</span></span> <span data-ttu-id="e0f27-120">それ以外の場合、ビジネス会議のため、Skype に接続されているサイズの大きいファイルは保持されません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0f27-120">Otherwise, a large file attached to a Skype for Business meeting might not be retained.</span></span> <span data-ttu-id="e0f27-121">Exchange オンライン PowerShell で、**セット-メールボックス MaxReceiveSize**と**セットのメールボックスの MaxSendSize**コマンドを使用する方法の詳細については、[一連のメールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0f27-121">For more information  about using the **Set-Mailbox -MaxReceiveSize** and **Set-Mailbox -MaxSendSize** commands in Exchange Online PowerShell, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).</span></span>
  
<span data-ttu-id="e0f27-122">保留リストに記載されていないメールボックスは、会議データを保存を必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e0f27-122">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="e0f27-123">などの 3 つの会議の参加者の 2 つのメールボックスが保持マークが付いている、会議データは、これら 2 つの参加者のメールボックスに保存されますが、3 つ目の参加者のメールボックスにメールボックスを持つではありませんを保持します。</span><span class="sxs-lookup"><span data-stu-id="e0f27-123">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e0f27-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e0f27-124">Related topics</span></span>
[<span data-ttu-id="e0f27-125">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="e0f27-125">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="e0f27-126">ブロック ポイント ツー ポイントのファイルの転送</span><span class="sxs-lookup"><span data-stu-id="e0f27-126">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="e0f27-127">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="e0f27-127">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="e0f27-128">組織内の会議ポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="e0f27-128">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
 