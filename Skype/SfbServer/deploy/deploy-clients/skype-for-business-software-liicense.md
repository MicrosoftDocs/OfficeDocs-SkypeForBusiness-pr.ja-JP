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
description: Skype for Business ソフトウェア ボリューム ライセンスを持っているかどうかを確認する方法については、このトピックを参照してください。
ms.openlocfilehash: 40b72e39fc0edc23b4cc0d17f82ba633c2ac24af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113093"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: Skype for Business ソフトウェア ライセンス
 
Skype for Business ソフトウェア ボリューム ライセンスを持っているかどうかを確認する方法については、このトピックを参照してください。 
  
Skype Room System は、インストールされている Skype for Business クライアントを使用します。ソフトウェア ボリューム ライセンスが必要です。 最初の Skype Room System を展開する前に、キー管理サーバー (KMS) または複数のライセンス認証キー (MAK) を使用して、展開のボリューム ライセンス状態を確認します。
  
## <a name="key-management-servers-kms"></a>キー管理サーバー (KMS)

KMS が配置され、Skype for Business ボリューム ライセンスのライセンス認証を配布する場合、Skype Room System は Skype for Business クライアントを自動的にアクティブ化します。 KMS が配置されているのを確認するには、次の方法を使用します。
  
コマンド プロンプトから、次のコマンドを実行します。  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
詳細については、「DNS 経由で windows KMS ホストOffice検出し、承認されていないインスタンス [を削除する方法」を参照してください](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。 
  
KMS を設定するには[、「KMS](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15))の KMS ライセンス認証と KMS Office 2013 [GVLK](/DeployOffice/vlactivation/gvlks)のライセンス認証」および「Active Directory のライセンス認証」を参照Office 2013
  
Office 2013 Lync の汎用ボリューム ライセンス キー: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (このキーを使用すると、Skype Room System はネットワーク上の KMS を探します)。
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>ボリューム ライセンス サービス センター (VLSC) からの複数のライセンス認証キー (MAK)

お客様が他のボリューム ライセンス ソフトウェアを使用している場合、IT 部門は VLSC を使用してソフトウェアライセンス認証とボリューム ライセンス契約 (VLA) を管理します。 これにより、会社は Skype for Business VL ライセンス認証を購入し、その後、Skype Room System 管理コンソールで入力用の MAK を取得できます。
  
VLAN をお持ちのお客様は、契約の管理および MAK の取得に使用される VLSC 資格情報を知っている必要があります。 不明な場合は、顧客の財務部門は、顧客が VLAN の支払いを行ったか確認できる必要があります。
  
MAK を取得するには、ボリューム ライセンス サービス センターにアクセスして契約を表示し、プロダクト キー (MAK) をダウンロードします。 詳細については、「ボリューム ライセンス サービス [センター」を参照してください](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MICROSOFT 365 または VLSC アクセスOffice 365 の MAK

顧客がボリューム ライセンス契約を締結しない場合、Skype for Business のライセンス認証は管理がはるかに困難になります。 ただし、VLSC アクセスのない Microsoft 365 および Office 365 のお客様は、Skype Room System を販売している OEM に次の情報を提供することで、プロモーション MAK を取得できます。
  
- 会社名
    
- 展開連絡先の名前、電子メール、および電話番号
    
- 展開されたシステムの数
    
- 展開日
    
- 顧客が Microsoft Technical Account Manager を持つ場合、TAM の名前と連絡先情報
