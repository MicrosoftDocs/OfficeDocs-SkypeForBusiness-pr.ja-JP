---
title: SkypeRoom System Skype for Business ソフトウェア ライセンス
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: このトピックを参照して、ソフトウェア ボリューム ライセンスをSkype for Businessする方法について説明します。
ms.openlocfilehash: dc605af5bc4f922e1da1669fb471ad46173a7646
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761575"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>SkypeRoom System: Skype for Business ソフトウェア ライセンス
 
このトピックを参照して、ソフトウェア ボリューム ライセンスをSkype for Businessする方法について説明します。 
  
SkypeRoom System はインストール済みのSkype for Businessクライアントを使用します。ソフトウェア ボリューム ライセンスが必要です。 最初の Skype Room System を展開する前に、キー管理サーバー (KMS) または複数のライセンス認証キー (MAK) を使用して、展開のボリューム ライセンス状態を確認します。
  
## <a name="key-management-servers-kms"></a>キー管理サーバー (KMS)

ボリューム KMSライセンス認証を配布する場合、Skype for Business Skypeルーム システムは自動的にクライアントをSkype for Businessします。 現在の場所にあるKMS確認するには、次の方法を使用します。
  
コマンド プロンプトから、次のコマンドを実行します。  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
KMSを設定するには[、「KMS 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15))の Office ライセンス認証」と「KMS [2013](/DeployOffice/vlactivation/gvlks)の Active Directory ライセンス認証Office」を参照してください。
  
Office 2013 Lync の汎用ボリューム ライセンス キー: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (このキーにより、Skype Room System はネットワーク上の KMS を探します)。
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>ボリューム ライセンス サービス センター (VLSC) からの複数のライセンス認証キー (MAK)

お客様が他のボリューム ライセンス ソフトウェアを使用している場合、IT 部門は VLSC を使用してソフトウェアライセンス認証とボリューム ライセンス契約 (VLA) を管理します。 これにより、会社は VL ライセンス認証Skype for Business購入し、その後、Skype Room System 管理コンソールで入力用の MAK を取得できます。
  
VLAN をお持ちのお客様は、契約の管理および MAK の取得に使用される VLSC 資格情報を知っている必要があります。 不明な場合は、顧客の財務部門は、顧客が VLAN の支払いを行ったか確認できる必要があります。
  
MAK を取得するには、ボリューム ライセンス サービス センターにアクセスして契約を表示し、プロダクト キー (MAK) をダウンロードします。 詳細については、「ボリューム ライセンス サービス [センター」を参照してください](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>VLSC アクセスのないMicrosoft 365またはOffice 365 MAK

お客様がボリューム ライセンス契約を締結しない場合、ライセンス認証Skype for Business管理がはるかに困難になります。 ただし、VLSC Microsoft 365アクセスOffice 365ユーザーとユーザーは、ルーム システムを販売している OEM に次の情報を提供することで、プロモーション MAK をSkypeできます。
  
- 会社名
    
- 展開連絡先の名前、電子メール、および電話番号
    
- 展開されたシステムの数
    
- 展開日
    
- 顧客が Microsoft Technical Account Manager を持つ場合、TAM の名前と連絡先情報
