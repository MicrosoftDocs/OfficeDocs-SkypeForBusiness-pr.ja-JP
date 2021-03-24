---
title: Skype for Business 会議に添付された大きなファイルを保持する
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Skype for Business 会議にファイルを添付すると、参加者はファイルを開いてダウンロードできます。 Skype for Business 会議に添付されたファイルは、メールボックスが訴訟ホールドに設定されている、Microsoft 365 または Office 365 アイテム保持ポリシーが適用されている、または Microsoft 365 コンプライアンス センターの電子情報開示ケースに関連付けられた保留にされている参加者のメールボックスに保持されます。 このコンテンツは、参加者のメールボックス内の回復可能なアイテム フォルダーに保存されます。
ms.openlocfilehash: 515f8b68db04a7acfc8eab2d7c639157cdb0da8d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100573"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="dcee5-105">Skype for Business 会議に添付された大きなファイルを保持する</span><span class="sxs-lookup"><span data-stu-id="dcee5-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="dcee5-106">Skype for Business 会議にファイルを添付すると、参加者はファイルを開いてダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="dcee5-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="dcee5-107">Skype for Business 会議に添付されたファイルは、メールボックスが訴訟ホールドに設定されている、Microsoft 365 または Office 365 アイテム保持ポリシーが適用されている、または Microsoft 365 コンプライアンス センターの電子情報開示ケースに関連付けられた保留にされている参加者のメールボックスに保持されます。</span><span class="sxs-lookup"><span data-stu-id="dcee5-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has a Microsoft 365 or Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Microsoft 365 Compliance Center.</span></span> <span data-ttu-id="dcee5-108">このコンテンツは、参加者のメールボックス **内の回復可能なアイテム** フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="dcee5-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="dcee5-109">保留されているメールボックスに保持されているファイルはインデックスが作成されるため、参加者のメールボックスを検索するときにセキュリティ コンプライアンス センターでコンテンツ検索を実行するときに検索 &amp; できます。</span><span class="sxs-lookup"><span data-stu-id="dcee5-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="dcee5-110">ただし、30 MB を超える添付ファイルは、2 つ以上の小さいファイルに分割され、圧縮 (.zip) ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="dcee5-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="dcee5-111">これらの  *小*  さいファイルのコンテンツは、検索用のインデックスが作成されていないので、コンテンツ検索で返されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="dcee5-111">The  *content*  of these smaller files is not indexed for search and might not be returned in a Content Search.</span></span> <span data-ttu-id="dcee5-112">ただし、 *これらのファイル*  のメタデータ (ファイル名や作成者など) は検索用にインデックスが作成され、コンテンツ検索で返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="dcee5-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search and might be returned in a Content Search.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dcee5-113">Exchange Online メールボックスの MaxReceiveSize と MaxSendSize の設定は、Skype for Business 会議から大きなファイルを保持する機能に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dcee5-113">The MaxReceiveSize and MaxSendSize settings for an Exchange Online mailbox can affect the ability to retain large files from Skype for Business meetings.</span></span> <span data-ttu-id="dcee5-114">MaxReceiveSize と MaxSendSize の既定の設定は、それぞれ 36 MB と 35 MB です。</span><span class="sxs-lookup"><span data-stu-id="dcee5-114">The default settings for MaxReceiveSize and MaxSendSize are 36 MB and 35 MB, respectively.</span></span> <span data-ttu-id="dcee5-115">ただし、これらの既定の設定は小さすぎて、30 MB を超える Skype for Business 会議のファイルを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcee5-115">However, these default settings are too small to retain any file from a Skype for Business meeting that's larger than 30 MB.</span></span> <span data-ttu-id="dcee5-116">これは、Exchange Online でメッセージ添付ファイルや他のバイナリ データの Base64 エンコードが使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="dcee5-116">This is because Exchange Online uses Base64 encoding of message attachments and other binary data.</span></span> <span data-ttu-id="dcee5-117">メッセージをエンコードすると、そのサイズは約 33% 増加します。</span><span class="sxs-lookup"><span data-stu-id="dcee5-117">When a message is encoded, its size is increased by approximately 33%.</span></span> <span data-ttu-id="dcee5-118">そのため、Skype for Business 会議の大きなファイルを確実に保持するには、保留にされたユーザーの MaxReceiveSize と MaxSendSize の両方の値を 39 MB に増やすることをお勧めします (前に説明した 30 MB のサイズ制限を約 33% 大きくします)。</span><span class="sxs-lookup"><span data-stu-id="dcee5-118">Therefore, to ensure that large files from Skype for Business meetings are retained, we recommend that you increase the value for both MaxReceiveSize and MaxSendSize to 39 MB (which is approximately 33% larger than the 30 MB size limit that was previously explained) for users who are placed on hold.</span></span> <span data-ttu-id="dcee5-119">そうしないと、Skype for Business 会議に添付された大きなファイルが保持されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dcee5-119">Otherwise, a large file attached to a Skype for Business meeting might not be retained.</span></span> <span data-ttu-id="dcee5-120">Exchange Online PowerShell で **Set-Mailbox -MaxReceiveSize** および **Set-Mailbox -MaxSendSize** コマンドを使用する方法の詳細については [、「Set-Mailbox」](/powershell/module/exchange/mailboxes/Set-Mailbox)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcee5-120">For more information  about using the **Set-Mailbox -MaxReceiveSize** and **Set-Mailbox -MaxSendSize** commands in Exchange Online PowerShell, see [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).</span></span>
  
<span data-ttu-id="dcee5-121">保留にされていないメールボックスには、会議データは保存されません。</span><span class="sxs-lookup"><span data-stu-id="dcee5-121">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="dcee5-122">たとえば、2 人の参加者のメールボックスに保持のマークが付いている 3 人の会議では、会議データは 2 人の参加者のメールボックスに保存されますが、メールボックスが保留されていない 3 人目の参加者のメールボックスには保存されません。</span><span class="sxs-lookup"><span data-stu-id="dcee5-122">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="dcee5-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcee5-123">Related topics</span></span>
[<span data-ttu-id="dcee5-124">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="dcee5-124">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="dcee5-125">ポイント間ファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="dcee5-125">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="dcee5-126">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="dcee5-126">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="dcee5-127">組織で会議ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="dcee5-127">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
