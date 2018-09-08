---
title: Skype ルーム システム v2 用のアカウントを構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ''
description: Exchange Skype ルーム システム v2 のアカウントを構成し、ビジネスの Skype の詳細については、このトピックを参照してください。
ms.openlocfilehash: 4070757324c9c0abf56cd623ce0155649e456e3b
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886486"
---
# <a name="configure-accounts-for-skype-room-systems-v2"></a>Skype ルーム システム v2 用のアカウントを構成します。
 
Skype ルーム システム v2 と交換し、ビジネスの Skype を統合する方法については、このトピックを参照してください。
  
このトピックでは、Microsoft Exchange、Skype の Skype ルーム システム v2 がビジネスに使用するアカウントを作成する方法について説明します。 Skype ルーム システム v2 デバイスの展開の手順については、 [Skype ルーム システム v2 のコンソールを構成](console.md)してください。 通常、インフラストラクチャは次のいずれかの構成に該当します。
  
- オンラインの展開: 組織の環境を Office 365 の完全に展開します。 詳細については、 [Office 365 で v2 を Skype ルーム システムの展開](with-office-365.md)を参照してください。
    
- 設置型展開: 組織が、制御しているサーバーは、Active Directory、Exchange、および Skype のビジネス サーバーがホストされています。 詳細については、[業務サーバーの Skype で v2 を Skype ルーム システムの展開](with-skype-for-business-server-2015.md)を参照してください。
    
- ハイブリッド展開: 設置型およびいくつかの Office 365 を通じてオンラインでホストでホストされているいくつかのサービスを組み合わせています。 Skype ルーム システム v2 では、ハイブリッドの次のシナリオがサポートされています。 
    
  - Exchange オンライン ビジネス上のサーバー設置型の Skype で。 詳細については、 [Exchange オンライン (ハイブリッド) と v2 を Skype ルーム システムの展開](with-exchange-online.md)を参照してください。
    
  - ビジネス オンラインの Skype では、社内設置型に交換します。 詳細については、[設置型 (ハイブリッド) 上での交換と v2 を Skype ルーム システムの展開](with-exchange-on-premises.md)を参照してください。
    
使用する構成は、デバイスのセットアップの準備方法に影響します。
  
Skype ルーム システム v2 では、Active Directory、Exchange、およびビジネスのための Skype は、[ユーザー アカウント] を指定する必要があります。 アカウントを使用して、その会議の予定表にアクセスし、Skype をビジネスの接続を確立します。 ユーザーは、このアカウントで会議をスケジュール設定することで、このアカウントを予約できます。 Skype ルーム システム v2 はその会議に参加し、会議の出席者にさまざまな機能を提供することになります。
  
> [!IMPORTANT]
> ユーザー アカウントがないと、これらの機能はいずれも動作しません。 
  
すべてのユーザー アカウントは 1 つの Skype ルーム システム v2 デバイスに一意であり、いくつかの設定が必要です。
  
- ユーザー アカウントは正しく構成する必要があります。
    
- Skype ルーム システム v2 のユーザー アカウントを検証し、適切な Microsoft サービスに到達できるようにするのには、お客様のインフラストラクチャを構成しなければなりません。
    
> [!IMPORTANT]
> ハードウェアを実際に設置するよりも十分に前もってアカウントを作成しておくことを、強くお勧めします。 設置の 2 週間から 3 週間前にアカウントの準備を開始するのが理想的です。 
  
ユーザー アカウントは、リソース アカウントのユーザーが、会議室の会議の空き容量またはのアカウントとして認識されると考えることができます。 こうした会議室を使用する会議を予約する場合は、そのアカウントを会議に招待します。 Skype ルーム システム v2 を最も効果的に使用するには、それぞれに割り当てられているユーザー アカウントを使用して同じを行います。
  
設定リソース メールボックスのアカウントが既に存在する場合に Skype ルーム システム v2 をインストールしている会議の場所に、ユーザー アカウントにそのリソースのアカウントを変更できます。 完了すると、実行する必要があります、Skype ルーム システム v2 デバイスへのユーザー アカウントの追加です。 下記のユーザー アカウントのセットアップ例を参照してください。
  
リモート管理は、 [Skype ルーム システムの計画 v2 管理 OMS を使用して](../../plan-your-deployment/clients-and-devices/oms-management.md)、 [OMS を使用して Skype ルーム システムの展開 v2 の管理](with-oms.md)、および管理の[で説明したように運用管理スイート (OMS) を使用して、追加の構成OMS を使用して Skype ルーム システム v2 のデバイス](../../manage/skype-room-systems-v2/oms.md)。 
  
## <a name="basic-configuration"></a>基本的な構成

これらのプロパティでは、Skype ルーム システム v2 を使用するユーザー アカウントの最小構成を表します。 ユーザー アカウントによっては、追加のセットアップが必要な場合があります。
  
|**プロパティ**|**用途**|
|:-----|:-----|
|Exchange メールボックス (Exchange 2013 SP1 以降、または Exchange のオンライン)  <br/> |Exchange メールボックスを持つアカウントを有効にすると、受信し、会議出席依頼、およびメールの両方を送信し、Skype ルーム システム v2 デバイス上の会議の予定表を表示する機能、ユーザー アカウントが与えられます。 Skype ルーム システム v2 のメールボックスは、会議室メールボックスである必要があります。  <br/> |
|ビジネス用の Skype が有効になっています。  <br/> |ビデオ通話、IM、および画面共有など、さまざまな会議機能を使用するためには、ビジネス用の Skype を有効にする必要があります。 ビジネス オンラインの Skype と Skype のビジネス サーバーの両方がサポートされています。  <br/> |
|パスワードが有効になっている  <br/> |パスワードを使ってユーザー アカウントを有効にする必要がありますか、ビジネスのサーバーの Exchange または Skype のいずれかで認証することはできません。  <br/> |
   
## <a name="advanced-configuration"></a>[詳細設定の構成

プロパティの中に基本的な構成が単純な環境で設定するユーザー アカウントを許可するには環境は、Skype ルーム システム v2 を正常に使用するために満たす必要のあるディレクトリのアカウントにその他の制限を持っている可能性のある、ユーザー アカウントです。
  
|**プロパティ**|**用途**|
|:-----|:-----|
|証明書ベースの認証  <br/> |証明書は、Exchange と Skype のビジネス サーバーの両方に必要な可能性があります。 証明書を展開するには、管理者としてログインしたときに証明書をロードできます。  <br/> |
   
ユーザー アカウントを設定する最も簡単な方法では、リモートの Windows PowerShell を使用してそれらを構成します。 マイクロソフトでは、 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、新しいユーザー アカウントを作成または Skype ルーム システム v2 の互換性のあるユーザー アカウントにそれらを有効にするためにある既存のリソース アカウントの検証を支援するスクリプトを提供します。
  
Windows PowerShell コマンドレット経由で Office 365 の UI を使用する場合は、いくつかの手順を手動で実行することができます。 [Office 365 を使用してデバイスのアカウントを作成する](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)を参照してください。
  
## <a name="see-also"></a>関連項目

[Skype Room Systems バージョン 2 の計画](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Skype Room Systems バージョン 2 コンソールを構成する](console.md)
  
[Skype Room Systems バージョン 2 を管理する](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

