---
title: "ビジネス会議のため、Skype に接続されている大容量のファイルを保持します。"
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
description: "Skype ビジネス会議、どの参加者を選択し、開いてできますし、ダウンロードのためにファイルを添付することができます。 Skype ビジネス会議のための添付ファイルはメールボックスを持つ証拠保全に、Office 365 リテンション ・ ポリシーが適用される、または Office 365 のセキュリティ、電子的証拠開示のケースに関連付けられている保留リストに配置されます。 任意の参加者のメールボックスに保持されます。&amp;コンプライアンス センターです。 このコンテンツは、自分のメールボックス内の参加者の回復可能なアイテム フォルダーに保存されます。"
ms.openlocfilehash: 59e1470d36aac988b1e0ff6ee40ebc1fb61967ed
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="7261e-105">ビジネス会議のため、Skype に接続されている大容量のファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="7261e-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="7261e-106">Skype ビジネス会議、どの参加者を選択し、開いてできますし、ダウンロードのためにファイルを添付することができます。</span><span class="sxs-lookup"><span data-stu-id="7261e-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="7261e-107">Skype ビジネス会議のための添付ファイルはメールボックスを持つ証拠保全に、Office 365 リテンション ・ ポリシーが適用される、または Office 365 のセキュリティ、電子的証拠開示のケースに関連付けられている保留リストに配置されます。 任意の参加者のメールボックスに保持されます。&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="7261e-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="7261e-108">このコンテンツは、自分のメールボックス内の参加者の**回復可能なアイテム**フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="7261e-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="7261e-109">保留中のメールボックスに保持されるファイルはインデックスが、セキュリティ コンテンツの検索を実行している場合、したがって検索できる&amp;コンプライアンス センターの関係者のメールボックスを検索する場合。</span><span class="sxs-lookup"><span data-stu-id="7261e-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="7261e-110">ただし、39 MB より大きい添付ファイルは 2 つ以上のサイズの小さいファイルに分割するには、圧縮 (.zip) ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="7261e-110">However, attached files that are larger than 39 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="7261e-111">これらの小さいファイルの*コンテンツ*は、検索、インデックス付けされていないと、コンテンツ検索では返されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7261e-111">The  *content*  of these smaller files is not indexed for search, and might not be returned in a Content Search.</span></span> <span data-ttu-id="7261e-112">ただし、これらのファイル (ファイル名や作成者) などの*メタデータ*検索、インデックスが作成され、コンテンツの検索で返される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7261e-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search, and might be returned in a Content Search.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7261e-113">メールボックスがいっぱいか、テナント管理者には、39 MB より小さくなるように MaxSendSize が構成されている場合は、ファイルのすべてのデータは保持されませんをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="7261e-113">If the mailbox is full or the tenant admin has configured MaxSendSize to be smaller than 39 MB, uploaded file data will not be retained at all.</span></span> <span data-ttu-id="7261e-114">MaxSendSize の既定値は 150 MB ですが、テナント管理者は、サイズは 1 MB に MaxSendSize を構成できます。</span><span class="sxs-lookup"><span data-stu-id="7261e-114">The default MaxSendSize is 150 MB, but tenant admins can configure MaxSendSize to be as small as 1 MB.</span></span> 
  
<span data-ttu-id="7261e-115">保留リストに記載されていないメールボックスは、会議データを保存を必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7261e-115">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="7261e-116">などの 3 つの会議の参加者の 2 つのメールボックスが保持マークが付いている、会議データは、これら 2 つの参加者のメールボックスに保存されますが、3 つ目の参加者のメールボックスにメールボックスを持つではありませんを保持します。</span><span class="sxs-lookup"><span data-stu-id="7261e-116">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7261e-117">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7261e-117">Related topics</span></span>
[<span data-ttu-id="7261e-118">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="7261e-118">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="7261e-119">ブロック ポイント ツー ポイントのファイルの転送</span><span class="sxs-lookup"><span data-stu-id="7261e-119">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="7261e-120">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="7261e-120">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="7261e-121">組織内の会議ポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="7261e-121">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  