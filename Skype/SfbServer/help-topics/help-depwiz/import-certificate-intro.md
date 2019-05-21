---
title: 証明書のインポート (開始)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: 証明書をインポートするには、証明書ファイルへのパスを指定する必要があります。 [証明書ファイルの選択] テキストボックスで、完全なパスとファイル名を入力するか、[参照] ボタンをクリックして、パスの場所とファイル名 (通常は、p7b、.pfx、または .cer ファイル) に移動します。
ms.openlocfilehash: b1bf46efaefb8a400158cac7ed5fd9527c7272f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273988"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="6dcd3-104">証明書のインポート (開始)</span><span class="sxs-lookup"><span data-stu-id="6dcd3-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="6dcd3-105">証明書をインポートするには、証明書ファイルへのパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dcd3-105">To import a certificate, you must provide a path to the certificate file.</span></span> <span data-ttu-id="6dcd3-106">**[証明書ファイルの選択**] テキストボックスで、完全なパスとファイル名を入力するか、[**参照**] ボタンをクリックして、パスの場所とファイル名 (通常は、p7b、.pfx、または .cer ファイル) に移動します。</span><span class="sxs-lookup"><span data-stu-id="6dcd3-106">In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="6dcd3-107">証明書に秘密キーが含まれている場合は、[証明書**ファイルに証明書の秘密キーが含まれてい**ます] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6dcd3-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="6dcd3-108">このチェックボックスをオンにすると、**パスワード**テキスト入力が有効になります。</span><span class="sxs-lookup"><span data-stu-id="6dcd3-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="6dcd3-109">秘密キーが関連付けられた証明書がある場合は、証明書の作成時にパスワードが通常秘密キーに設定されます。</span><span class="sxs-lookup"><span data-stu-id="6dcd3-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="6dcd3-110">秘密キーのパスワードを入力して、証明書と秘密キーを証明書ストアにインポートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="6dcd3-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="6dcd3-111">証明書ファイルのパスの情報を入力し、必要に応じて秘密キーのパスワードを指定した場合は、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dcd3-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6dcd3-112">秘密キーのパスワードがわからない場合、インポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6dcd3-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

