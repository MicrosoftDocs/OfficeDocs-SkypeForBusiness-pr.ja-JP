---
title: 割り当てられていない電話番号 新規の作成または既存の編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: 未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。
ms.openlocfilehash: 51c3f640bd9d98bcda9d5dd69406461e9c8393fd
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711744"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="76e6c-104">割り当てられていない電話番号: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="76e6c-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="76e6c-p102">未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。</span><span class="sxs-lookup"><span data-stu-id="76e6c-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76e6c-p103">新しい未使用の番号範囲の作成または既存の未使用の番号範囲の編集が終了して [**OK**] をクリックすると、[**未使用の番号**] ページに戻り、すべての番号範囲が表示されます。[**新規 未使用の番号範囲**] ページまたは [**編集 未使用の番号範囲**] ページで行った変更は、[**未使用の番号**] ページで [**すべてコミット**] をクリックするまでは、データベースにコミットされません。</span><span class="sxs-lookup"><span data-stu-id="76e6c-p103">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges. The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="76e6c-109">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="76e6c-109">UI Reference</span></span>

<span data-ttu-id="76e6c-110">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="76e6c-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="76e6c-111">**名前** 割り当てられていない番号範囲を識別するわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="76e6c-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="76e6c-112">範囲を保存した後、この名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="76e6c-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="76e6c-113">**数値範囲** 最初のフィールドに、割り当てられていない番号範囲の先頭番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="76e6c-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="76e6c-114">2 番目のフィールドに、範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="76e6c-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="76e6c-115">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="76e6c-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="76e6c-116">範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76e6c-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="76e6c-117">数値は正規表現と一致する必要があります `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` 。</span><span class="sxs-lookup"><span data-stu-id="76e6c-117">The number must match the regular expression `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?`.</span></span> <span data-ttu-id="76e6c-118">つまり、数値は文字列で始まる可能性があります (文字列を指定しない場合は自動的に追加されます)、プラス記号 (+)、および数字 1 ~ `tel:` 9 です。</span><span class="sxs-lookup"><span data-stu-id="76e6c-118">This means the number may begin with the string `tel:` (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="76e6c-119">電話番号には最大 17 桁の数字を指定できます。その後に内線番号 ;ext= の後に内線番号を付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="76e6c-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="76e6c-120">**アナウンス サービス** アナウンス **アプリケーションが** 着信呼び出しまたは **Exchange UM** を処理するには、[アナウンス] を選択して、着信呼び出しを処理自動応答 Exchange UM を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="76e6c-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="76e6c-121">[**アナウンス サービス**] で [**アナウンス**] を選択した場合:</span><span class="sxs-lookup"><span data-stu-id="76e6c-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="76e6c-122">**宛先サーバーの FQDN** 割り当てられていないこの範囲の着信呼び出しを処理するアナウンス アプリケーションを実行する Application サービスのサービス ID を選択します。</span><span class="sxs-lookup"><span data-stu-id="76e6c-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="76e6c-123">**お知らせ** 割り当てられていないこの範囲の番号に対して再生するアナウンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="76e6c-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="76e6c-124">[**アナウンス サービス**] で [**Exchange UM**] を選択した場合:</span><span class="sxs-lookup"><span data-stu-id="76e6c-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="76e6c-125">**自動応答電話番号** Exchange UM サーバーの電話番号を自動応答。</span><span class="sxs-lookup"><span data-stu-id="76e6c-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="76e6c-126">お知らせの機能の詳細については、「計画」のドキュメントの「Plan for the [Announcement application in Skype for Business 2015」](../../plan-your-deployment/enterprise-voice-solution/announcement.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76e6c-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="76e6c-127">未使用の番号範囲の操作の詳細については、「操作」のドキュメントの「[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76e6c-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


