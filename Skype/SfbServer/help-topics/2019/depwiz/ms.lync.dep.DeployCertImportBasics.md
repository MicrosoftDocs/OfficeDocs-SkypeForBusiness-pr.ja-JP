---
title: 証明書のインポート (開始)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
ROBOTS: NOINDEX, NOFOLLOW
description: 証明書をインポートするには、証明書ファイルへのパスを指定する必要があります。 [証明書ファイルの選択] テキスト ボックスに完全なパスとファイル名を入力するか、[参照] ボタンをクリックしてパスの場所に移動し、ファイル名 (通常は、.p7b、.pfx、または .cer ファイル) をクリックすることができます。
ms.openlocfilehash: ec0eb1593c628e44fcbe5cfb8d47a381b9281406
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837107"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="29486-104">証明書のインポート (開始)</span><span class="sxs-lookup"><span data-stu-id="29486-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="29486-p102">証明書をインポートするには、証明書ファイルへのパスを指定する必要があります。**[証明書ファイルの選択]** テキスト ボックスに完全なパスとファイル名を入力するか、**[参照]** ボタンをクリックしてパスの場所に移動し、ファイル名 (通常は、.p7b、.pfx、または .cer ファイル) をクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="29486-p102">To import a certificate, you must provide a path to the certificate file. In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="29486-107">証明書にプライベート キーが含まれている場合は、[証明書ファイルに証明書のプライベート キーが含まれている **] チェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="29486-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="29486-108">このチェック ボックスを選択すると、**[パスワード]** テキスト入力が有効になります。</span><span class="sxs-lookup"><span data-stu-id="29486-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="29486-109">秘密キーが関連付けられている証明書がある場合、通常は、証明書の作成時にパスワードが指定されています。</span><span class="sxs-lookup"><span data-stu-id="29486-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="29486-110">証明書と秘密キーを証明書ストアにインポートできるようにするため、秘密キーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="29486-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="29486-111">証明書ファイルのパス情報を入力し、必要に応じオプションで秘密キーのパスワードを入力したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29486-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="29486-112">秘密キーのパスワードが不明な場合にはインポートに失敗します。</span><span class="sxs-lookup"><span data-stu-id="29486-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

