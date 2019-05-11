---
title: Skype ルーム システムの Skype のビジネス ソフトウェアのライセンス
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: このトピックでは、Skype for Business ソフトウェア ボリューム ライセンスがあるかどうかを確認する方法について説明します。
ms.openlocfilehash: 8bc8abfb4b379faaf94ac8cf8fbf4fdb792329bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893348"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: Skype for Business ソフトウェア ライセンス
 
このトピックでは、Skype for Business ソフトウェア ボリューム ライセンスがあるかどうかを確認する方法について説明します。 
  
Skype ルームのシステムでは、ビジネスのクライアントは、ソフトウェアのボリューム ライセンスが必要ですがインストールされている Skype を使用します。 Skype の最初の部屋のシステムを展開する前に、キー マネージメント サーバー (KMS) またはマルチ ライセンス認証キー (MAK) を使用して、展開のボリューム ライセンスの状態を確認します。
  
## <a name="key-management-servers-kms"></a>キー管理サーバー (KMS)

KMS では、ビジネスのボリューム ライセンスのアクティブ化の Skype を配布、Skype ルーム システムは、Skype クライアントのビジネスを自動的にアクティブになります。 KMS が配置されているかどうかを確認するには、次の手順を実行します。
  
コマンド ・ プロンプトから次のコマンドを実行します。`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
詳細については、 [DNS を使用して、Office と Windows の KMS ホストを検出し、不正なインスタンスを削除する方法](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)を参照してください。 
  
KMS を設定するには、 [Office 2013 の KMS ライセンス認証](https://technet.microsoft.com/library/ee624357.aspx)と[の Office 2013 KMS と Active Directory のライセンス認証のための GVLKs](https://technet.microsoft.com/library/dn385360.aspx)を参照してください。
  
Lync の Office 2013 汎用ボリューム ライセンス キー: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (このキーと、ネットワーク上の KMS を検索する Skype ルーム システムのことです)。
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>ボリューム ライセンス サービス センター (VLSC) からのマルチ ライセンス認証キー (MAK)

顧客が他のボリューム ライセンス ソフトウェアを使用している場合、IT 部門では VLSC を使用してソフトウェア ライセンス認証およびボリューム ライセンス契約 (VLA) を管理します。 ビジネスのボリューム ライセンスのアクティブ化、会社になる Skype ルーム システム管理コンソールでの入力を MAK を取得できるため、Skype を購入する企業にもできます。
  
VLA を保持する顧客は、契約を管理し、MAK を取得するために使用する自身の VLSC 資格情報を確認する必要があります。 、不明な場合は、お客様の財務部門がの VLA のお客様が支払われたかどうかを確認すること場合があります。
  
MAK を取得するには、ボリューム ライセンス サービス センターにアクセスして契約を表示し、プロダクト キー (MAK) をダウンロードしてください。 詳細については、[ボリューム ライセンス サービス センター](https://www.microsoft.com/Licensing/servicecenter/default.aspx)を参照してください。 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>VLSC アクセスのない Office 365 用の MAK

お客様は、ボリューム ライセンス契約を割り当てられていない、ビジネスのアクティベーションのための Skype を管理する非常に困難になります。 ただし、VLSC にアクセスすることがなく、Office 365 のお客様を入手できますプロモーション MAK OEM に次の情報を提供することで Skype ルーム システムの販売。
  
- 会社名
    
- 展開の連絡先名、メール、および電話番号
    
- 展開されたシステムの数
    
- 展開日
    
- お客様は、Microsoft テクニカル アカウント マネージャー、TAM の名前および連絡先情報を持っている場合
    

