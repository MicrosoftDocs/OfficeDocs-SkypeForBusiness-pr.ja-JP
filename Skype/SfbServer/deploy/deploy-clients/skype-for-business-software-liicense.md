---
title: Skype Room System Skype for Business ソフトウェアライセンス
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: このトピックでは、Skype for Business ソフトウェアボリュームライセンスがあるかどうかを確認する方法について説明します。
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220927"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: Skype for Business ソフトウェアライセンス
 
このトピックでは、Skype for Business ソフトウェアボリュームライセンスがあるかどうかを確認する方法について説明します。 
  
Skype Room System は、インストールされている Skype for Business クライアントを使用します。これにはソフトウェアボリュームライセンスが必要です。 最初の Skype Room System を展開する前に、キー管理サーバー (KMS) またはマルチライセンス認証キー (MAK) を使用して、展開のボリュームライセンスの状態を確認してください。
  
## <a name="key-management-servers-kms"></a>キー管理サーバー (KMS)

KMS が設定されている場合、Skype for Business ボリュームライセンスのライセンス認証が配布されると、skype Room System は自動的に Skype for Business クライアントをアクティブにします。 KMS が適切であるかどうかを確認するには、次のようにします。
  
コマンドプロンプトで、次を実行します。`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
詳細については、「DNS を使用して[Office および WINDOWS KMS ホストを検出して、権限のないインスタンスを削除する方法](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)」を参照してください。 
  
Kms をセットアップするには、「 [office 2013 の kms ライセンス認証](https://technet.microsoft.com/library/ee624357.aspx)」および「 [OFFICE 2013 の Kms と Active Directory ライセンス認証用の GVLKs](https://technet.microsoft.com/library/dn385360.aspx) 」を参照してください。
  
Office 2013 の一般的なボリュームライセンスキー Lync: 23BNTT KDQW3-TCK7R (このキーを使用すると、Skype Room System によってネットワーク上の KMS が検索されます)。
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>ボリュームライセンスサービスセンター (VLSC) からのマルチライセンス認証キー (MAK)

お客様が他のボリュームライセンスソフトウェアを使用している場合は、IT 部門が VLSC を使用してソフトウェアのライセンス認証とボリュームライセンス契約 (VLA) を管理します。 これにより、会社で skype for Business VL ライセンス認証を購入できるようになります。これにより、会社は Skype Room System 管理コンソールで入力の MAK を取得することができます。
  
VLA を使用しているお客様は、VLSC の資格情報を知っている必要があります。これは、契約を管理し、MAK を取得するために使用されます。 ご不明な場合は、お客様の財務部門が、VLA に対してお客様が支払ったかどうかを確認できる必要があります。
  
MAK を取得するには、ボリュームライセンスサービスセンターにアクセスして、契約書を表示し、プロダクトキー (MAK) をダウンロードします。 詳細については、[ボリュームライセンスサービスセンター](https://www.microsoft.com/Licensing/servicecenter/default.aspx)にアクセスしてください。 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>VLSC アクセスなしの MAK for Microsoft 365 または Office 365

お客様がボリュームライセンス契約を所有していない場合は、Skype for Business のライセンス認証をより簡単に管理できます。 ただし、Microsoft 365 および Office 365 のお客様は、VLSC アクセスを行わない場合は、Skype Room System を販売している OEM に次の情報を提供することで、販促用の MAK を取得できます。
  
- 会社名
    
- 展開連絡先の名前、電子メール、電話番号
    
- 展開されているシステムの数
    
- 展開日
    
- お客様が Microsoft テクニカルアカウントマネージャーを持っている場合は、TAM の名前と連絡先情報
    

