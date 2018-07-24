---
title: 割り当てられていない電話番号を新規作成または既存の編集
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。
ms.openlocfilehash: 27ac407fa07926c70c6a3897edcab009a5382462
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982112"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="86dd1-104">割り当てられていない電話番号: 新規作成または既存の編集</span><span class="sxs-lookup"><span data-stu-id="86dd1-104">Unassigned Phone Number: Create New or Edit Existing</span></span>
 
<span data-ttu-id="86dd1-p102">未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。</span><span class="sxs-lookup"><span data-stu-id="86dd1-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="86dd1-107">新しい割り当てられていない番号範囲を作成または既存の編集が終了したら、すべての数値の範囲を示す**番号が割り当てられていない**ページに戻るには **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="86dd1-107">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="86dd1-108">**新しい未割り当ての番号範囲**] ページまたは **[割り当てられていない番号 Rage の編集**ページに加えた変更は、[**割り当てられていない番号**] ページ**のすべてのコミット**をクリックするまでにはデータベースにコミットされません。</span><span class="sxs-lookup"><span data-stu-id="86dd1-108">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="86dd1-109">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="86dd1-109">UI Reference</span></span>

<span data-ttu-id="86dd1-110">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="86dd1-110">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="86dd1-111">**名**未使用の番号の範囲を識別するわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="86dd1-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="86dd1-112">範囲を保存すると、この名前は変更できません。</span><span class="sxs-lookup"><span data-stu-id="86dd1-112">After you save the range, this name cannot be changed.</span></span>
    
- <span data-ttu-id="86dd1-113">**番号の範囲**最初のフィールドに割り当てられていない番号の範囲の開始番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="86dd1-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="86dd1-114">2 番目のフィールドには、範囲の終了番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="86dd1-114">In the second field, type the ending number of the range.</span></span>
    
  - <span data-ttu-id="86dd1-115">範囲の開始番号が終了番号より大きくならないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="86dd1-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
  - <span data-ttu-id="86dd1-116">範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86dd1-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
  - <span data-ttu-id="86dd1-117">番号が正規表現に一致する必要があります (tel:) ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?。</span><span class="sxs-lookup"><span data-stu-id="86dd1-117">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="86dd1-118">つまり、番号の先頭に文字列 tel: (その文字列を指定しない場合に自動的に追加)、プラス記号 (+) と数字の 1 9 から。</span><span class="sxs-lookup"><span data-stu-id="86dd1-118">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="86dd1-119">電話番号が最大 17 桁にすることができ、拡張した形式で続いて ext = 内線番号の後にします。</span><span class="sxs-lookup"><span data-stu-id="86dd1-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
- <span data-ttu-id="86dd1-120">**サービスのお知らせ****発表**のお知らせアプリケーションが着信呼び出しを処理するか、 **Exchange UM**を Exchange UM 自動応答着信呼び出しを処理するを選択します。</span><span class="sxs-lookup"><span data-stu-id="86dd1-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>
    
- <span data-ttu-id="86dd1-121">**お知らせサービス**の**お知らせ**を選択した場合。</span><span class="sxs-lookup"><span data-stu-id="86dd1-121">If you selected **Announcement** for **Announcement service**:</span></span>
    
  - <span data-ttu-id="86dd1-122">**宛先サーバーの FQDN**この範囲の割り当てられていない番号への着信呼び出しを処理するアナウンス アプリケーションを実行するアプリケーション サービスのサービス ID を選択します。</span><span class="sxs-lookup"><span data-stu-id="86dd1-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>
    
  - <span data-ttu-id="86dd1-123">**お知らせ**この割り当てられていない番号の範囲を再生するアナウンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="86dd1-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>
    
-  <span data-ttu-id="86dd1-124">**Exchange UM** **サービスのお知らせ**を選択した場合。</span><span class="sxs-lookup"><span data-stu-id="86dd1-124">If you selected **Exchange UM** for **Announcement service**:</span></span>
    
  - <span data-ttu-id="86dd1-125">**自動応答の電話番号**Exchange UM 自動応答の電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="86dd1-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>
    
<span data-ttu-id="86dd1-126">発表の特徴と機能についての詳細は、計画ドキュメントに[ビジネス用の Skype で知らせアプリケーションの計画](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86dd1-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="86dd1-127">割り当てられていない番号範囲の操作についての詳細は、操作マニュアル[を構成するルーティングの割り当てられていない電話番号](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86dd1-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>
  

