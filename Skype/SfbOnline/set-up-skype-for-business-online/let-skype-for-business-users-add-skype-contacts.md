---
title: Skype for Business ユーザーが Skype の連絡先を追加できるようにする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: '組織外からのビジネス ユーザー向けのビジネス用連絡先 Skype の Skype を使用しているし、連絡先の一覧に追加するユーザーをできるようにする方法を参照してください。 '
ms.openlocfilehash: 212393154cb2b730ce18f5be9b03495e747e207c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885462"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Skype for Business ユーザーが Skype の連絡先を追加できるようにする

ビジネスの Skype で、検索でき、Skype では、無料のアプリケーションを使用して他のユーザーとの IM! この資料では、Skype 連絡先を追加するために必要なものについて説明します。 
  
これを行う Office 365 の[管理者のアクセス許可](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)が必要です。

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**
  
1. Office 365 の管理者アカウントを使用してサインイン[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)。
    
2. Office 365 管理センターでは、**管理センター**に移動 > **ビジネス用の Skype**です。 
    
    ![ビジネス管理センターの Skype を選択します。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. **ビジネス管理センターの Skype**では、**組織**を選択します。 > **外部との連絡**。 
    
4. 既定では、ユーザーは、(これを許可するファイアウォールが構成されていると仮定した場合)、ビジネスの Skype を使用している世界中の他のすべてのユーザーと通信できます。 
    
    ![Let を選択してユーザーは、Skype で通信するためにビジネス用の Skype を使用します。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Skype ユーザーとチャットするのには、ユーザーが、ビジネスの Skype を使用している他のユーザーとチャットすることをしない**にのみ許可されるドメイン**を選択します。 Skype ユーザーと連絡先を有効にすると、skype.com は自動的にバック グラウンドで許可されているドメインとして追加されます。 
    
    特定の場合を除き、ビジネスの Skype を使用して世界中の他のすべての企業からの連絡を許可するを選択する場合は**でブロックされたドメインを除く**を選択し、**+** それらのドメインを追加するのには。 除くこれらの特定のドメイン上のユーザーに連絡して誰もができます。 (一部の企業は、このオプションを選択などの訴訟では、そのことを確認する必要がある場合は、他のビジネスとの接続)。
    
5. **ユーザーが組織外の Skype ユーザーと通信するビジネス用の Skype を使用できるように**選択してください。 
    
6.  Windows ファイアウォールを使用している場合は、Skype のビジネスに必要なポートが自動的に開きます。
    
    組織では、インターネットへの接続をネットワーク上のコンピューターを制限するのには別のソリューションを使用している場合は、クライアント コンピューターはすべての[IP アドレスや Url](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)の Skype の接続」と「Skype ディレクトリ検索にアクセスすることを確認します。 これは、必要がありますファイアウォールまたはプロキシ インフラストラクチャの構成で許可リストを送信に追加します。
    
7. **テストするのには最大で 24 時間を待機**します。 外部通信の設定を変更するすべてのデータ センター間で設定を変更するには、最大 24 時間かかります。
    
8. 検索し、Skype の連絡先を Skype のビジネス用連絡先の一覧に追加する方法をユーザーに表示します。 [ビジネス用の Skype で人を検索](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19)するには、それらをポイントします。
    
## <a name="test-and-troubleshoot"></a>テストし、トラブルシューティング

設定をテストするには、企業ファイアウォールの背後にあるではない Skype の連絡先が必要です。 Gmail アカウント、Outlook.com アカウント、または他の種類の電子メール アカウントを使用して Skype に、署名できます。
  
1. **24 までの待機時間をテスト**外部の通信設定を変更した場合。
    
2. ビジネス用の Skype からサインアウトし、サインインし直して、Skype ディレクトリを検索するオプションを表示するようにします。 
    
    ![Skype ディレクトリをハイライト表示すると、Skype のアカウントを持っている人を検索できます。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. ビジネス用の Skype、Skype では、[連絡先の検索し、チャットへの要求を送信します。 
    
    会社のポリシーのために送信できませんでした、メッセージが表示される場合は、[ファイアウォールの設定](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)を再確認してくださいする必要があります。 
    
4. 問題は、ファイアウォールのないファイアウォールの内側に、コーヒー ショップなどの wifi の場所に移動し、ビジネスの Skype を使用して、Skype に要求を送信するかどうかをテストする別の方法では、チャットにお問い合わせください。 
    
   - **Skype 相手に要求を送信しそれを受信したことはないかどうかは**、チャットへの要求を送信するよう依頼します。 問題は、Skype と Skype のビジネスとの間の接続を確立することが、多くの場合解決されることです。
    
   - メッセージはコーヒー ショップを通過し、問題がわかっていないしたら職場場合、は、ファイアウォールです。 
    
## <a name="what-you-can-and-cant-do"></a>できるタスクとタスクを実行できません。

- **Mac でのビジネス用の Skype**を検索し、Skype の連絡先と通信する機能がありません。
    
- ディレクトリ検索を有効にすると、検索し、Skype と Skype をビジネス ユーザーに検索できます。 何らかの理由により、ディレクトリを検索して見つからないときにすることができます依頼、連絡先を送信し、Skype にサインインし、同意する場合は、そのためできます IM に。 
    
- Google や Facebook などの他の IM プロバイダーとの IM 接続を許可することはできません。 携帯電話のテキスト メッセージを送信するビジネス用の Skype を使うことはできません。

- オーディオの録音またはビジネス用連絡先の連絡先を Skype と Skype との間のビデオ通話をすることはできません。
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>どのような機能は、Skype 連絡先を追加するときに使用しますか。

Microsoft アカウント (以前 Windows Live ID) を使用して署名した Skype の連絡先は、いくつかを取得できますが、Skype をビジネス ユーザー向けに、通信機能のすべてではありません。
  
|**Skype の連絡先で使用できます。**|**Skype の連絡先では利用できません。**|
|:-----|:-----|
| ビデオ会話 <br/>  ユーザー間のインスタント メッセージング <br/>  プレゼンス <br/> | マルチパーティ IM 会話 <br/>  3 人以上のオーディオとビデオ会話 <br/>  デスクトップとプログラムの共有 <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連トピック

[外部の Skype for Business ユーザーに連絡できるようにする](allow-users-to-contact-external-skype-for-business-users.md)
  
[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

  
 
