---
title: "ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/23/2018
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: "ユーザーが組織外からビジネス ユーザーのビジネス用連絡先 Skype の Skype を使用しているし、連絡先リストに追加できるようにする方法を参照してください。 "
ms.openlocfilehash: 0e74cfb8efb08da404f0fdc9be611d9a3239d90f
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。

Skype for Business を使ってユーザーを検索できますと Skype、無料のアプリを使用しているすべてのユーザーとの IM を使用します。この記事では、Skype の連絡先を追加するために必要な情報について説明します。 
  
これを行う Office 365 の[管理者権限](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)が必要です。
  
1. [Https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)で Office 365 の管理者アカウントでサインインします。
    
2. Office 365 管理センターで、**管理センター**に移動 > **Skype for Business**します。 
    
    ![Skype for Business 管理センター] を選びます。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. **Skype for Business 管理センター**で、[**組織**] を選びます > **外部通信**します。 
    
4. 既定では、ユーザーは、(この操作を許可するファイアウォールが構成されている場合) 向けの Skype を使用している、世界中の他のすべてのユーザーに連絡できます。 
    
    ![選択できるようにユーザーが Skype との通信に Skype for Business を使用します。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    ユーザーが、Skype ユーザーとチャットする向けの Skype を使用している他のユーザーとチャットするようにしたくない場合は、 **[許可ドメインのみ**を選択します。Skype ユーザーと連絡先を有効にしたときに skype.com が行われる処理できるドメインとして自動的に追加します。 
    
    向け、Skype を使用して特定の送信を除く、世界中に他のすべての企業から連絡先を許可する、選択する場合**の禁止ドメイン以外**、] を選びます**+**これらのドメインを追加します。すべてのユーザーは、これらの特定のドメインでユーザーを除く連絡することはできます。(企業によっては、このオプションを選択、たとえば、訴訟では、ことを確認する必要がある場合がないとその他のビジネス用連絡先)
    
5. **Skype for Business、組織外の Skype ユーザーとやり取りする際に使用できるように**する] を選びます。 
    
6.  Windows ファイアウォールを使っている場合は、Skype for Business が自動的に必要なポートを開きます。
    
    組織では、インターネットに接続するネットワーク上のコンピューターを制限するに別のソリューションを使用している場合は、クライアント コンピューターは、すべての[IP アドレスと Url](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)の Skype の接続」と「Skype ディレクトリ検索にアクセスすることを確認します。これが必要になるファイアウォールまたはプロキシ インフラストラクチャ構成] ボックスの一覧を許可する、送信に追加します。
    
7. **テストするのには、最大 24 時間かかる**。外部通信] 設定を変更するには、すべてのデータ センターで設定を変更するには、最大 24 時間がかかることができます。
    
8. ユーザーの検索し、Skype のビジネス用連絡先の一覧に Skype の連絡先を追加する方法を示します。[Skype for Business で連絡先を検索](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19)するには、それらをポイントします。
    
## <a name="test-and-troubleshoot"></a>テスト、トラブルシューティングする.

設定をテストするのには、会社のファイアウォールの背後にない人 Skype で連絡先を必要があります。これらは、Gmail アカウントを Outlook.com アカウント、またはその他のメール アカウントの種類を使って Skype へのサインインことができます。
  
1. した後、 **24 まで待機する時間にテスト**の外部通信設定を変更します。
    
2. 向けに Skype をサインアウトして、もう一度サインインため、Skype ディレクトリを検索する] オプションが表示します。 
    
    ![Skype ディレクトリを強調表示されたら、Skype アカウントを所有するユーザーを検索できます。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. Skype for Business] で、Skype の連絡先を検索し、[チャット出席依頼を送信します。 
    
    会社のポリシーが原因でそれを送信できなかったメッセージが表示される場合は、[ファイアウォールの設定](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)を確認してくださいする必要があります。 
    
4. 問題は、ファイアウォール、喫茶店など、ファイアウォールの背後にあるいない wifi 場所に移動し、Skype for Business を使って Skype に要求を送信するかどうかをテストする別の方法では、チャットにお問い合わせください。 
    
  - **Skype 連絡先要求を送信して受信することがないかどうかは**、チャット、出席依頼を送信するように依頼します。問題は、Skype と Skype for Business の間の接続を確立するが、多くの場合が解決されることです。
    
  - 今すぐメッセージ喫茶店を通過するのにいないしたら職場で、[問題の場合は、ファイアウォールです。 
    
## <a name="what-you-can-and-cant-do"></a>何を実行できません。

- **Skype for Business Mac で**検索して、Skype の連絡先と通信する機能がありません。
    
- ディレクトリの検索を有効にすると、検索、ビジネス ユーザーの Skype と Skype を検索することができます。ディレクトリを検索することにより、それらを見つけられない何らかの理由を連絡先の依頼を送信して、[Skype にサインインし、同意してができる場合、im を送信できますにします。 
    
- 場合によっては、Google、Facebook などの他の IM プロバイダーとの IM 接続を許可することはできません。携帯電話のテキスト メッセージを送信するのには、Skype for Business を使うことはできません。
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Skype の連絡先を追加するときに、どのような機能を使えますか。

Microsoft アカウント (旧 Windows Live ID) を使ってサインインした Skype の連絡先は、いくつかにアクセスできる、Skype for Business ユーザーと通信するときに、すべての機能はします。
  
|**Skype の連絡先との連絡可能**|**Skype の連絡先では使用できません。**|
|:-----|:-----|
| ビデオ会話 <br/>  ユーザー間のインスタント メッセージング <br/>  プレゼンス <br/> | マルチパーティ IM での会話 <br/>  3 つ以上のユーザーとの音声とビデオの会話 <br/>  デスクトップとプログラムの共有 <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連トピック

[ビジネス ユーザー向けの Skype の外部の連絡先にユーザーを許可します。](allow-users-to-contact-external-skype-for-business-users.md)
  
[Skype for Business Online をセットアップします。](set-up-skype-for-business-online.md)
