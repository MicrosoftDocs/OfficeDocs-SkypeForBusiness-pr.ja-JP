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
description: 'Skype for Business を使用しているユーザーが、組織外の Skype for Business ユーザーと連絡を取り、連絡先の一覧に追加できるようにする方法を説明します。 '
ms.openlocfilehash: 212393154cb2b730ce18f5be9b03495e747e207c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238034"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Skype for Business ユーザーが Skype の連絡先を追加できるようにする

Skype for Business では、ユーザーは無料アプリ Skype を使用するすべての人を検索し、インスタント メッセージ (IM) を送信することができます! この記事では、Skype の連絡先を追加するために必要な操作について説明します。 
  
Office 365 でこれを行うには、[管理者アクセス許可](https://support.office.com/ja-JP/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)が必要です。

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**
  
1. [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) で、Office 365 管理者アカウントを使用してサインインします。
    
2. Office 365 管理センターから **[管理センター** > **[Skype for Business]** の順に移動します。 
    
    ![Skype for Business 管理センターを選択します。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. **Skype for Business 管理センター**で、[**組織**]  >  [**外部通信**] の順に選択します。 
    
4. 既定では、ユーザーは Skype for Business を使用している世界中の他のすべてのユーザーと通信できます (ファイアウォールがこれを許可するように構成されていると仮定します)。 
    
    ![[ユーザーが Skype for Business を使用して Skype と通信できるようにする] を選択します。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    ユーザーが Skype ユーザーとチャットできても、Skype for Business を使用している他のユーザーとはチャットできないようにする場合は、**[許可されたドメインに対してのみ有効にする]** を選択します。 Skype ユーザーとの連絡を有効にすると、skype.com が許可されたドメインとして、自動的にバックグラウンドで追加されます。 
    
    特定の連絡先を除く、Skype For Business を使用する世界中のすべての企業からの通信を許可する場合、**[ブロックされたドメインを除く]** を選択し、**[+]** を選択して、該当するドメインを追加します。 その特定ドメインのユーザーを除く、すべてのユーザーと通信できるようになります。 (たとえば一部の企業では、訴訟において相手企業と接触していないことを確証する必要があるため、このオプションを選択する場合があります。)
    
5. **[ユーザーが Skype for Business を使用して組織外の Skype と通信できるようにする]** を選択します。 
    
6.  Windows ファイアウォールを使用している場合、Skype for Business では必要なポートが自動的に開きます。
    
    組織が、別のソリューションを使用して、ネットワーク上のコンピューターのインターネット接続を制限している場合は、クライアント コンピューターがすべての [IP アドレスと URI](https://support.office.com/ja-JP/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) にアクセスして Skype 接続と Skype ディレクトリ検索を実行できるようにします。 この場合、ファイアウォールまたはプロキシ インフラストラクチャ構成で、それらを送信許可リストに追加する必要がある可能性があります。
    
7. **テストするため最大 24 時間待ちます**。 外部通信の設定を変更すると、すべてのデータ センターに変更が反映されるまでに最大で 24 時間かかる場合があります。
    
8. ユーザーに、Skype for Business の連絡先の一覧に Skype の連絡先を検索し追加する方法を伝えます。 「[Skype for Business で知り合いを検索する](https://support.office.com/ja-JP/article/b12500ef-e37f-4d22-aade-c11277e53f19)」を参照してもらいます。
    
## <a name="test-and-troubleshoot"></a>テストとトラブルシューティング

設定をテストするには、会社のファイアウォールの外側にいる Skype の連絡先が必要です。 Gmail アカウント、Outlook.com アカウント、その他のメール アカウントを使用して、Skype にサインインできます。
  
1. 外部通信設定を変更した後、**テストするため最大 24 時間待ちます**。
    
2. Skype for Business からサインアウトし、もう一度サインインすると、Skype ディレクトリの検索オプションが表示されます。 
    
    ![Skype ディレクトリが強調表示されていたら、Skype アカウントを持つユーザーを検索できます。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. Skype for Business で、Skype の連絡先を検索し、チャットの要求を送信します。 
    
    会社のポリシーが原因で送信できないというメッセージが表示される場合、[ファイアウォール設定](https://support.office.com/ja-JP/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)を再度確認する必要があります。 
    
4. 問題の原因がお客様のファイアウォールかどうかを別の方法でテストするには、ファイアウォールの外側の WiFi エリア (カフェなど) に行き、Skype for Business を使用して Skype の連絡先にチャットの要求を送信します。 
    
   - **Skype の連絡先にリクエストを送信したのに相手が受け取っていない場合**、チャットの要求を送信するように依頼します。 Skype と Skype for Business 間の接続の確立に問題が発生していた場合は、たいていこれで解決します。
    
   - メッセージをカフェからは送信できる一方、職場からは送信できない場合は、問題の原因は職場のファイアウォールであることが特定できます。 
    
## <a name="what-you-can-and-cant-do"></a>実行できること、できないこと

- **Mac 版 Skype for Business** では、Skype の連絡先を検索し通信する機能はありません。
    
- ディレクトリの検索を有効にすると、Skype ユーザーや Skype for Business ユーザーを検索できます。 何らかの理由でディレクトリを検索しても見つからない場合は、連絡先リクエストを送信して、Skype にサインインして同意してもらうことで、インスタント メッセージ (IM) の送信が可能になります。 
    
- Google、Facebook などの他の IM プロバイダーとの IM 接続を許可することはできません。 Skype for Business を使用して、携帯電話のテキスト メッセージを送信することはできません。

- Skype の連絡先と Skype for Business の連絡先の間でオーディオまたはビデオ通話を記録することはできません。
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Skype の連絡先を追加すると、どんな機能を使えますか?

Microsoft アカウント (以前の Windows Live ID) でサインインしている Skype の連絡先は、Skype for Business ユーザーとの通話時に一部の機能を使えますが、すべての機能が使用できるわけではありません。
  
|**Skype の連絡先との間で利用できる機能**|**Skype の連絡先との間で利用できない機能**|
|:-----|:-----|
| ビデオ会話 <br/>  ユーザー間のインスタント メッセージング <br/>  プレゼンス <br/> | マルチ パーティの IM 会話 <br/>  3 人以上でのオーディオやビデオによる会話 <br/>  デスクトップとプログラムの共有 <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連トピック

[ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](allow-users-to-contact-external-skype-for-business-users.md)
  
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

  
 
