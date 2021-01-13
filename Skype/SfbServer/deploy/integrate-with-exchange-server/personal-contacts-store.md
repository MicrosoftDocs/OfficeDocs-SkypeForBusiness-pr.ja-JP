---
title: Lync 2010 クライアント コンピューターで個人用連絡先ストアを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '概要: 従来のクライアントで使用される個人用連絡先ストアを構成します。'
ms.openlocfilehash: 66ef1c3726ea020669894769b48b2313e1da2e0e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833937"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="407ad-103">Lync 2010 クライアント コンピューターで個人用連絡先ストアを構成する</span><span class="sxs-lookup"><span data-stu-id="407ad-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="407ad-104">Skype for Business Server 2015 と Exchange Server 2016 または Exchange Server 2013 を統合している場合は、クライアントが使用する個人用連絡先ストアを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="407ad-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="407ad-105">特に、Exchange を個人用連絡先ストアとして使用する Skype for Business を構成し、同時に、ユーザーが決定を上書きできないのを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="407ad-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="407ad-106">これは、各クライアント コンピューターでレジストリ値を作成および構成することで実行できます。</span><span class="sxs-lookup"><span data-stu-id="407ad-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="407ad-107">次の手順は、Lync 2010 クライアント以前を使用するクライアントでのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="407ad-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="407ad-108">Lync 2013 クライアントとすべての Skype for Business クライアントには、連絡先ストアの設定を上書きするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="407ad-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="407ad-109">ある 1 台のコンピューターでこの値を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="407ad-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="407ad-110">クライアント コンピューターで、[スタート] ボタンを **クリックし** 、[ファイル名を指定して実行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="407ad-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="407ad-111">[ファイル名 **を指定して** 実行] ダイアログ ボックスに「regedit」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="407ad-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="407ad-112">レジストリ エディターで、[ HKEY_LOCAL_MACHINE] を展開し **、[** ソフトウェア] を展開し、[**ポリシー**] を展開し、[ **Microsoft]** を展開して、[ Communicator **。**</span><span class="sxs-lookup"><span data-stu-id="407ad-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="407ad-113">ユーザー設定を右 **Communicator、[** 新規] をポイントし **、[DWORD (32 ビット) 値] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="407ad-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="407ad-114">新しい値を作成した後、「PersonalContactStoreOverride」と入力し、Enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="407ad-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="407ad-115">PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディタを閉じます。</span><span class="sxs-lookup"><span data-stu-id="407ad-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="407ad-116">複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="407ad-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="407ad-117">Windows 10 でこれを行う方法について詳しくは、グループ ポリシー オブジェクトの作成に関する記事 [をご覧](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) ください。</span><span class="sxs-lookup"><span data-stu-id="407ad-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
