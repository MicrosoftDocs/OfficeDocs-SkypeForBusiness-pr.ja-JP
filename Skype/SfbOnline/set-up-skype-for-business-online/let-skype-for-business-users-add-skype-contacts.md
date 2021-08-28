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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: '組織外のユーザーにSkype for BusinessをSkype for Businessして、連絡先の一覧に追加する方法を確認します。 '
ms.openlocfilehash: 77fb8098e7adeebd4267aed7f21153b20abd661b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594841"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Skype for Business ユーザーが Skype の連絡先を追加できるようにする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

このSkype for Business、ユーザーは無料のアプリである Skypeを使用しているすべてのユーザーと IM を検索して IM を実行できます。 この記事では、連絡先に連絡先を追加するために必要なSkype説明します。 
  
この操作を[行うには、Microsoft 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)またはOffice 365アクセス許可が必要です。

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**
  
1. で管理者アカウントMicrosoft 365またはOffice 365サインインします [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) 。
    
2. 管理センターで、[管理センター]**に移動Skype for Business。**  >   
    
    ![管理センター Skype for Business選択します。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. **Skype for Business 管理センター** で、[**組織**]  >  [**外部通信**] の順に選択します。 
    
4. 既定では、ユーザーは Skype for Business を使用する世界中の他のすべてのユーザーと通信できます (ファイアウォールがこれを許可するように構成されている場合)。 
    
    ![[ユーザーが他のユーザーとSkype for Business通信を行うSkype。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    ユーザーが Skype ユーザーとチャットする必要があるが、Skype for Business を使用する他のユーザーとチャットしたくない場合は、[許可されているドメイン] に対して [オン] を **選択します**。 ユーザーとの連絡先を有効Skype、skype.com が許可されたドメインとして自動的に追加されます。 
    
    特定のドメインを除き、Skype for Business を使用して世界中の他のすべての企業からの連絡先を許可する場合は、[ブロックされているドメインを除いてオン] を選択し、それらのドメインを追加します。 **+** これらの特定のドメインのユーザーを除き、すべてのユーザーから連絡を受け取る可能性があります。 (一部の企業では、このオプションを選択する場合があります。たとえば、訴訟中で、他のビジネスとの連絡が取り合えない場合など)。
    
5. [**ユーザーが組織外Skype for Businessユーザーと通信Skypeを使用する] を選択します**。 
    
6.  ファイアウォールを使用している場合Windows必要Skype for Businessポートが自動的に開きます。
    
    組織が別のソリューションを使用してネットワーク上のコンピューターのインターネットへの接続を制限している場合は、クライアント コンピューターが Skype 接続と Skype ディレクトリ検索のすべての IP アドレスと[URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)にアクセスできる必要があります。 これには、ファイアウォールまたはプロキシ インフラストラクチャ構成の送信許可リストに追加する必要がある場合があります。
    
7. **テストするには、最大 24 時間待機します**。 外部通信設定を変更すると、すべてのデータ センターに変更が設定されるのに最大 24 時間かかる場合があります。
    
8. 連絡先を検索して追加する方法をユーザーにSkypeリストに追加する方法Skype for Businessします。 [ユーザーを[検索] をポイントSkype for Business。](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19)
    
## <a name="test-and-troubleshoot"></a>テストとトラブルシューティング

セットアップをテストするには、会社のファイアウォールの背後にSkypeの連絡先が必要です。 Gmail アカウント、Skype.com アカウント、または他の種類のメール アカウントを使用して、Outlook にサインインできます。
  
1. 外部通信の設定を変更した後、テスト **するまで最大 24 時間待ちます**。
    
2. Skype for Businessサインアウトしてから、もう一度サインインすると、ディレクトリを検索するオプションがSkypeされます。 
    
    ![[Skype] が強調表示されている場合は、アカウントを持つユーザー Skypeできます。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. [Skype for Business] で連絡先を検索しSkypeチャットに要求を送信します。 
    
    会社のポリシーが原因で送信できなかったというメッセージが表示された場合は、ファイアウォール設定 をダブルチェックする [必要があります](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。 
    
4. ファイアウォールが問題かどうかをテストするもう 1 つの方法は、コーヒー ショップなどのファイアウォールの背後ではない Wi-Fi の場所に移動し、Skype for Business を使用してチャットに Skype 連絡先に要求を送信する方法です。 
    
   - **お客様がリクエストをSkypeし**、そのリクエストを受け取らない場合は、チャットへのリクエストを送信してください。 問題がアプリケーションとネットワークの間の接続を確立Skype場合Skype for Business、多くの場合、問題は解決します。
    
   - コーヒー ショップでメッセージが送信されるが、仕事中ではない場合は、ファイアウォールが問題であるのがわかっています。 
    
## <a name="what-you-can-and-cant-do"></a>実行できる操作と実行できない操作

- **Skype for Business Mac では**、連絡先を検索してコミュニケーションを取る機能Skypeがあります。
    
- ディレクトリ検索が有効になっている場合は、ユーザーを検索してSkype検索Skype for Businessできます。 何らかの理由でディレクトリを検索して見つからなかった場合は、連絡先要求を送信し、Skype にサインインして承諾して、IM を送信できます。 
    
- Google や Facebook などの他の IM プロバイダーとの IM 接続を許可できない。 携帯電話のテキスト メッセージをSkype for Businessを使用することはできません。

- 連絡先と連絡先の間で音声通話やビデオ通話Skype録音Skype for Businessはできません。
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>連絡先を追加するときに使用できる機能Skype?

Skype Microsoft アカウント (以前の Windows Live ID) でサインインした連絡先は、Skype for Business ユーザーと話している場合、一部の機能を取得できますが、すべてではありません。
  
|**連絡先とSkype可能**|**他の連絡先ではSkypeできません**|
|:-----|:-----|
| ビデオの会話 <br/>  ユーザー間のインスタント メッセージング <br/>  プレゼンス <br/> | マルチパーティ IM 会話 <br/>  3 人以上のユーザーとの音声およびビデオの会話 <br/>  デスクトップとプログラムの共有 <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連トピック

[外部の Skype for Business ユーザーに連絡できるようにする](allow-users-to-contact-external-skype-for-business-users.md)
  
[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

  
 
