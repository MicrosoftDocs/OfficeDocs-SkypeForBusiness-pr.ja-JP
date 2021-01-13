---
title: Skype Room System Skype for Business ソフトウェア ライセンス
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: このトピックでは、Skype for Business ソフトウェア ボリューム ライセンスを持っているかどうかを確認する方法について説明します。
ms.openlocfilehash: 20e04f69ba5a931bae6ac8598567165a7a6043a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833927"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: Skype for Business ソフトウェア ライセンス
 
このトピックでは、Skype for Business ソフトウェア ボリューム ライセンスを持っているかどうかを確認する方法について説明します。 
  
Skype Room System は、ソフトウェア ボリューム ライセンスが必要な、インストール済みの Skype for Business クライアントを使用します。 最初の Skype Room System を展開する前に、キー管理サーバー (KMS) またはマルチ ライセンス認証キー (MAK) を使用して、展開のボリューム ライセンスの状態を確認します。
  
## <a name="key-management-servers-kms"></a>キー管理サーバー (KMS)

KMS が配置され、Skype for Business ボリューム ライセンスのライセンス認証を配布する場合、Skype Room System は Skype for Business クライアントを自動的にライセンス認証します。 KMS が配置されている場合は、次の方法を使用します。
  
コマンド プロンプトで、次のコマンドを実行します。  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
詳細については、「DNS 経由で windows KMS ホストOffice検出し、承認されていないインスタンスを削除する方法 [を参照してください](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。 
  
KMS をセットアップするには[、KMS](https://technet.microsoft.com/library/ee624357.aspx)の Office 2013 と[VLKS](https://technet.microsoft.com/library/dn385360.aspx)の KMS ライセンス認証と、ライセンス認証の Active Directory ライセンス認証を参照Office 2013
  
Office 2013 Lync の汎用ボリューム ライセンス キー: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (このキーにより、Skype Room System はネットワーク上の KMS を探します)。
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>ボリューム ライセンス サービス センター (VLSC) からのマルチ ライセンス認証キー (MAK)

お客様が他のボリューム ライセンス ソフトウェアを使用している場合、IT 部門は VLSC を使用してソフトウェアライセンス認証とボリューム ライセンス契約 (VLAN) を管理します。 これにより、会社は Skype for Business VL ライセンス認証を購入し、その後、Skype Room System 管理コンソールで入力用の MAK を取得できます。
  
VLAN を持つお客様は、契約の管理と MAK の取得に使用される VLSC 資格情報を知っている必要があります。 不明な場合、顧客の財務部門は、顧客が VLAN の支払いを行ったか確認できる必要があります。
  
MAK を取得するには、ボリューム ライセンス サービス センターにアクセスして契約を表示し、プロダクト キー (MAK) をダウンロードします。 詳細については、ボリューム ライセンス サービス [センターにアクセスしてください](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>VLSC にアクセスしない Microsoft 365 Office 365 の MAK

お客様がボリューム ライセンス契約を持たなかった場合、Skype for Business のライセンス認証の管理は非常に困難になります。 ただし、VLSC にアクセスOffice Microsoft 365 および Office 365 のお客様は、Skype Room System を販売する OEM に次の情報を提供することで、プロモーション用の MAK を取得できます。
  
- 会社名
    
- 展開連絡先の名前、電子メール、電話番号
    
- 展開されたシステムの数
    
- 展開日
    
- 顧客が Microsoft テクニカル アカウント マネージャーを持つ場合、TAM の名前と連絡先情報
    

