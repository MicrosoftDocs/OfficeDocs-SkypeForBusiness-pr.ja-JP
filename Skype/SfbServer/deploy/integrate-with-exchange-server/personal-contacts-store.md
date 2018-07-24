---
title: ビジネス サーバーのクライアント コンピューターで Skype の連絡先ストアを構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '概要: 2016 の Exchange Server や Exchange Server 2013 Skype ビジネス サーバーの使用、個人の連絡先ストアを構成します。'
ms.openlocfilehash: 311bab825412bae79c240ddb0f923c693b97103e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012901"
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server"></a><span data-ttu-id="7b593-103">ビジネス サーバーのクライアント コンピューターで Skype の連絡先ストアを構成します。</span><span class="sxs-lookup"><span data-stu-id="7b593-103">Configure the personal contacts store on client computers for Skype for Business Server</span></span>
 
<span data-ttu-id="7b593-104">**の概要:** 2016 の Exchange Server や Exchange Server 2013 Skype ビジネス サーバーの使用、個人の連絡先ストアを構成します。</span><span class="sxs-lookup"><span data-stu-id="7b593-104">**Summary:** Configure the personal contact store used by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="7b593-105">ビジネス サーバーと Exchange Server 2016 または Exchange Server 2013 の Skype を統合する場合は、Skype のビジネスを実行している任意のクライアント コンピューターで個人用の連絡先ストアを構成してください。</span><span class="sxs-lookup"><span data-stu-id="7b593-105">If you are integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store on any client computers running Skype for Business.</span></span> <span data-ttu-id="7b593-106">具体的には、Skype をビジネスで個人の連絡先ストアとして Exchange を使用し、同時に、ユーザーは、その判断をオーバーライドできないことを確認しますを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b593-106">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="7b593-107">そのためには、各クライアント コンピューターでレジストリ値を作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="7b593-107">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
<span data-ttu-id="7b593-108">ビジネス用の Skype を実行するコンピューターでこの必要はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7b593-108">Note that this is not required on computers running Skype for Business.</span></span>
  
<span data-ttu-id="7b593-109">1 台のコンピューターでこの値を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7b593-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="7b593-110">クライアント コンピューターで [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b593-110">On the client computer, click **Start** and then click **Run**.</span></span>
    
2. <span data-ttu-id="7b593-111">[**ファイル名を指定して実行**] ダイアログ ボックスで「regedit」と入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7b593-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
    
3. <span data-ttu-id="7b593-112">レジストリ エディターで、[**HKEY_LOCAL_MACHINE**]、[**Software**]、[**Policies**]、[**Microsoft**]、[**Communicator**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="7b593-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
    
4. <span data-ttu-id="7b593-113">[**Communicator**] を右クリックし、[**新規**] をポイントし、[**DWORD (32 ビット) 値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b593-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
    
5. <span data-ttu-id="7b593-114">新しい値を作成した後に「PersonalContactStoreOverride」と入力し、Enter キーを押して値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="7b593-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
    
6. <span data-ttu-id="7b593-115">PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7b593-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>
    
<span data-ttu-id="7b593-116">複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7b593-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="7b593-117">詳細については、グループ ポリシーのマニュアルを参照してください[https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543)。</span><span class="sxs-lookup"><span data-stu-id="7b593-117">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span></span>
  

