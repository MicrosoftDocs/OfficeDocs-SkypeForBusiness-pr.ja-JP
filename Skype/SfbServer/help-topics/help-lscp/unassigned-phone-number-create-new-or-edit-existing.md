---
title: 未割り当ての電話番号の新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: 未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。
ms.openlocfilehash: e8a294273591969430abbbc450a37a5292fbe0c1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685670"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="d2a84-104">割り当てられていない電話番号: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="d2a84-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="d2a84-p102">未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d2a84-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2a84-107">割り当てられていない新しい番号範囲の作成または既存の番号範囲の編集が完了したら、[ **OK]** をクリックして、すべての数値範囲を一覧表示する [**未使用の番号**] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="d2a84-107">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="d2a84-108">[未使用の番号 **] ページで**行った変更、または [割り当てられていない番号の**編集** **] ページで**[**コミット**] をクリックするまで、データベースにコミットされません。</span><span class="sxs-lookup"><span data-stu-id="d2a84-108">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d2a84-109">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="d2a84-109">UI Reference</span></span>

<span data-ttu-id="d2a84-110">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="d2a84-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="d2a84-111">**名前**割り当てられていない番号の範囲を示すわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2a84-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="d2a84-112">範囲を保存した後は、この名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d2a84-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="d2a84-113">**数値の範囲**最初のフィールドに、割り当てられていない番号の範囲の開始番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2a84-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="d2a84-114">2番目のフィールドに、範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2a84-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="d2a84-115">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="d2a84-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="d2a84-116">範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2a84-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="d2a84-117">数値は正規表現 (tel:) に一致する必要があります。 (\+)?[1-9] \d{0,17}(; ext = [1-9] \d{0,9})?</span><span class="sxs-lookup"><span data-stu-id="d2a84-117">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="d2a84-118">これは、数値が文字列 "tel" で始まる可能性があることを意味します (この文字列は自動的に追加されるように指定していない場合)。プラス記号 (+)、1 ~ 9 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="d2a84-118">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="d2a84-119">電話番号は最大17桁で、その後に形式の内線番号、内線番号、内線番号が続く場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2a84-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="d2a84-120">**アナウンスメントサービス**[**お知らせ**] を選択すると、アナウンスメントアプリケーションは着信通話または**exchange um**を処理して、着信呼び出しを処理します。</span><span class="sxs-lookup"><span data-stu-id="d2a84-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="d2a84-121">**アナウンスメントサービス**で**お知らせ**を選択した場合:</span><span class="sxs-lookup"><span data-stu-id="d2a84-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="d2a84-122">**転送先サーバーの FQDN**この範囲の未割り当て番号への着信通話を処理するアナウンスメントアプリケーションを実行するアプリケーションサービスのサービス ID を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2a84-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="d2a84-123">**お知らせ**この範囲の未割り当ての番号に対して再生するお知らせを選択します。</span><span class="sxs-lookup"><span data-stu-id="d2a84-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="d2a84-124">**EXCHANGE UM**で**お知らせサービス**を選択した場合:</span><span class="sxs-lookup"><span data-stu-id="d2a84-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="d2a84-125">**自動応答の電話番号**Exchange UM 自動応答の電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2a84-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="d2a84-126">お知らせ機能と機能の詳細については、計画ドキュメントの「 [Skype For business 2015 でのお知らせアプリケーションの計画](../../plan-your-deployment/enterprise-voice-solution/announcement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2a84-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="d2a84-127">未使用の番号範囲の使用の詳細については、「操作」のドキュメントの「[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2a84-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


