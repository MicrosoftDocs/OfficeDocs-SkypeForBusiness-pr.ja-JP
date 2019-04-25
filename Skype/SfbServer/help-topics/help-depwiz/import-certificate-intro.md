---
title: 証明書のインポート (開始)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: 証明書をインポートするには、証明書ファイルへのパスを提供する必要があります。 [証明書のファイルのテキスト ボックスで、いずれかの完全なパスとファイル名を入力または [参照] ボタンをクリックしてパスの場所とファイル名 (通常、.p7b、.pfx、または .cer ファイル) に移動します。
ms.openlocfilehash: 5006fa68b4b19fe312d92a3dc641f1ab61638e72
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234998"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="af3b1-104">証明書のインポート (開始)</span><span class="sxs-lookup"><span data-stu-id="af3b1-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="af3b1-105">証明書をインポートするには、証明書ファイルへのパスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af3b1-105">To import a certificate, you must provide a path to the certificate file.</span></span> <span data-ttu-id="af3b1-106">**[証明書ファイル**] ボックスに、いずれかの完全なパスとファイル名を入力または [**参照**] ボタンをクリックしてパスの場所とファイル名 (通常、.p7b、.pfx、または .cer ファイル) に移動します。</span><span class="sxs-lookup"><span data-stu-id="af3b1-106">In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="af3b1-107">証明書に秘密キーが含まれている場合は、**証明書ファイルに証明書の秘密キーが含まれている**チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="af3b1-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="af3b1-108">このチェック ボックスをオンにすると、**パスワード**のテキスト入力が有効になります。</span><span class="sxs-lookup"><span data-stu-id="af3b1-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="af3b1-109">それに関連付けられた秘密キーと証明書があれば、証明書が作成されると、パスワードが秘密キーに通常配置されます。</span><span class="sxs-lookup"><span data-stu-id="af3b1-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="af3b1-110">秘密キー証明書を許可して、証明書ストアにインポートする秘密キーのパスワードを入力するとします。</span><span class="sxs-lookup"><span data-stu-id="af3b1-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="af3b1-111">指定すると、情報の証明書ファイルのパス、および必要に応じて秘密キーのパスワードが必要な場合、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af3b1-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="af3b1-112">秘密キーのパスワードがわからない場合、インポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="af3b1-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

