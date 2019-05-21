---
title: Skype for Business 会議に添付されている大きなファイルを保持する
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
f1keywords: None
ms.custom:
- Setup
description: Skype for Business 会議にファイルを添付することができます。これにより、参加者はこの会議を開いてダウンロードすることができます。 Skype for Business 会議に添付されたファイルは、メールボックスが訴訟ホールドの対象になっているか、Office 365 アイテム保持ポリシーが適用されているか、Office 365 セキュリティの電子情報開示ケースに関連付けられている保留リストに含まれているすべての参加者のメールボックスに保持されます&amp;コンプライアンスセンター。 このコンテンツは、自分のメールボックスの参加者の [回復可能なアイテム] フォルダーに保存されます。
ms.openlocfilehash: 4a8022b522f933ff8897586f632764eda77c6a67
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297761"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="d0c7e-105">Skype for Business 会議に添付されている大きなファイルを保持する</span><span class="sxs-lookup"><span data-stu-id="d0c7e-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="d0c7e-106">Skype for Business 会議にファイルを添付することができます。これにより、参加者はこの会議を開いてダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="d0c7e-107">Skype for Business 会議に添付されたファイルは、メールボックスが訴訟ホールドの対象になっているか、Office 365 アイテム保持ポリシーが適用されているか、Office 365 セキュリティの電子情報開示ケースに関連付けられている保留リストに含まれているすべての参加者のメールボックスに保持されます&amp;コンプライアンスセンター。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="d0c7e-108">このコンテンツは、自分のメールボックスの参加者の [**回復可能なアイテム**] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="d0c7e-109">保留中のメールボックスに保存されているファイルはインデックス処理されるので、参加者のメール&amp;ボックスを検索するときに、セキュリティコンプライアンスセンターでコンテンツ検索を実行すると検索できます。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="d0c7e-110">ただし、30 MB を超える添付ファイルは、2つ以上の小さいファイルに分割され、圧縮 (.zip) ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="d0c7e-111">これらの小さいファイルの*内容*は検索用にインデックスされず、コンテンツ検索で返されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-111">The  *content*  of these smaller files is not indexed for search and might not be returned in a Content Search.</span></span> <span data-ttu-id="d0c7e-112">ただし、これらのファイルの*メタデータ*(ファイル名や作成者など) は検索用にインデックス処理されるため、コンテンツ検索で返される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search and might be returned in a Content Search.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d0c7e-113">Exchange Online メールボックスの MaxReceiveSize と MaxSendSize の設定は、Skype for Business 会議から大きいファイルを保持する機能に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-113">The MaxReceiveSize and MaxSendSize settings for an Exchange Online mailbox can affect the ability to retain large files from Skype for Business meetings.</span></span> <span data-ttu-id="d0c7e-114">MaxReceiveSize と MaxSendSize の既定の設定は、それぞれ 36 MB と 35 MB です。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-114">The default settings for MaxReceiveSize and MaxSendSize are 36 MB and 35 MB, respectively.</span></span> <span data-ttu-id="d0c7e-115">ただし、これらの既定の設定は、30 MB を超える Skype for Business 会議のファイルを保持するには小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-115">However, these default settings are too small to retain any file from a Skype for Business meeting that's larger than 30 MB.</span></span> <span data-ttu-id="d0c7e-116">これは、Exchange Online でメッセージの添付ファイルとその他のバイナリデータの Base64 エンコードが使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-116">This is because Exchange Online uses Base64 encoding of message attachments and other binary data.</span></span> <span data-ttu-id="d0c7e-117">メッセージがエンコードされると、サイズは約 33% 増加します。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-117">When a message is encoded, its size is increased by approximately 33%.</span></span> <span data-ttu-id="d0c7e-118">そのため、Skype for Business 会議から大きいファイルが保持されるようにするには、MaxReceiveSize と MaxSendSize の値を 39 MB に増やすことをお勧めします (これについては、前に説明した 30 MB のサイズ制限より約 33% 大きくなります)。保留中のユーザーの場合。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-118">Therefore, to ensure that large files from Skype for Business meetings are retained, we recommend that you increase the value for both MaxReceiveSize and MaxSendSize to 39 MB (which is approximately 33% larger than the 30 MB size limit that was previously explained) for users who are placed on hold.</span></span> <span data-ttu-id="d0c7e-119">そうしないと、Skype for Business 会議に添付されている大きなファイルが保持されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-119">Otherwise, a large file attached to a Skype for Business meeting might not be retained.</span></span> <span data-ttu-id="d0c7e-120">Exchange Online PowerShell での**MaxReceiveSize**と set-Mailbox **-maxsendsize**コマンドの使用について詳しくは、「[メールボックスを設定](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-120">For more information  about using the **Set-Mailbox -MaxReceiveSize** and **Set-Mailbox -MaxSendSize** commands in Exchange Online PowerShell, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).</span></span>
  
<span data-ttu-id="d0c7e-121">保留になっていないメールボックスには、会議データが保存されません。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-121">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="d0c7e-122">たとえば、2人の参加者のメールボックスが保持対象としてマークされている会議では、会議データは、その2人の出席者のメールボックスに保存されます。ただし、メールボックスは保留中ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0c7e-122">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d0c7e-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d0c7e-123">Related topics</span></span>
[<span data-ttu-id="d0c7e-124">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d0c7e-124">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="d0c7e-125">ポイントツーポイントファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="d0c7e-125">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="d0c7e-126">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="d0c7e-126">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="d0c7e-127">組織内の会議ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="d0c7e-127">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
 