---
title: Skype Room System Skype for Business ソフトウェアライセンス
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: このトピックでは、Skype for Business ソフトウェア ボリューム ライセンスがあるかどうかを確認する方法について説明します。
ms.openlocfilehash: 15f768de96d65cd8584ceb2529b92892a7a94afe
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774816"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: Skype for Business ソフトウェア ライセンス
 
このトピックでは、Skype for Business ソフトウェア ボリューム ライセンスがあるかどうかを確認する方法について説明します。 
  
Skype Room System はインストールされた Skype for Business クライアントを使用します。これにはソフトウェアボリュームライセンスが必要です。 最初の Skype Room システムを展開する前に、キー管理サーバー (KMS) または複数のライセンス認証キー (MAK) を使用した展開のボリュームライセンスの状態を確認してください。
  
## <a name="key-management-servers-kms"></a>キー管理サーバー (KMS)

KMS が設定されていて、Skype for business ボリュームライセンスのライセンス認証が行われると、skype Room システムは自動的に Skype for Business クライアントをアクティブ化します。 KMS が配置されているかどうかを確認するには、次の手順を実行します。
  
コマンドプロンプトで次を実行します。`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
詳細については、「 [DNS を使用して Office および Windows の KMS ホストを見つけて、未承認のインスタンスを削除する方法](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)」を参照してください。 
  
KMS をセットアップするには、「 [office 2013 および GVLKs の kms のライセンス](https://technet.microsoft.com/library/ee624357.aspx)認証と[Office 2013 の Active Directory のライセンス認証を](https://technet.microsoft.com/library/dn385360.aspx)行う」を参照してください。
  
Lync 用の Office 2013 汎用ボリュームライセンスキー: 23BNTT 3G-KDQW3-TCK7R (このキーによって、Skype Room System がネットワーク上の KMS を検索します)。
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>ボリューム ライセンス サービス センター (VLSC) からのマルチ ライセンス認証キー (MAK)

顧客が他のボリューム ライセンス ソフトウェアを使用している場合、IT 部門では VLSC を使用してソフトウェア ライセンス認証およびボリューム ライセンス契約 (VLA) を管理します。 これにより、会社は skype for Business VL のライセンス認証を購入することもできます。その後、会社は Skype Room System 管理コンソールで入力の MAK を取得できます。
  
VLA を保持する顧客は、契約を管理し、MAK を取得するために使用する自身の VLSC 資格情報を確認する必要があります。 未定の場合、お客様の財務部門は、お客様が VLA の支払いを行ったかどうかを確認できます。
  
MAK を取得するには、ボリューム ライセンス サービス センターにアクセスして契約を表示し、プロダクト キー (MAK) をダウンロードしてください。 詳細については、[ボリュームライセンスサービスセンター](https://www.microsoft.com/Licensing/servicecenter/default.aspx)を参照してください。 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>VLSC アクセスのない Office 365 用の MAK

お客様がボリュームライセンス契約を持っていない場合、Skype for Business のライセンス認証は、より簡単に管理することが難しくなります。 ただし、VLSC アクセスのない Office 365 のお客様は、次の情報を Skype Room システムを販売する OEM に提供することにより、プロモーションの MAK を取得できます。
  
- 会社名
    
- 展開の連絡先名、メール、および電話番号
    
- 展開されたシステムの数
    
- 展開日
    
- 顧客が Microsoft のテクニカルアカウントマネージャーを持っている場合、TAM の名前と連絡先情報
    

