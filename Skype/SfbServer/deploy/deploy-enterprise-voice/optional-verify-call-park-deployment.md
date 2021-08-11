---
title: (省略可能)[通話パークの展開を確認する] Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: コール パークの展開をSkype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 1c07b8f3c94a05b7a3f896537b2c0f05d7c0e381fa80ef8b67562854fedc4bf8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298657"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(省略可能)[通話パークの展開を確認する] Skype for Business
 
コール パークの展開をSkype for Business Server エンタープライズ VoIP。 
  
コール パークをインストールして構成した後、構成を確認して、駐車場と呼び出しの取得が期待通り動作する必要があります。 少なくとも、以下を確認してください。
  
- 通話パークが有効になっているユーザーを呼び出し、ユーザーに通話をパークします。
    
    > [!NOTE]
    > このテストを実行する直前に音声ポリシーで通話パークを有効にした場合、通話を駐車しているユーザーは Skype for Business からサインアウトしてからサインインし、転送呼び出しリストに [通話パーク] オプションを表示できる必要があります。 
  
- オービット番号をダイヤルして、電話を取ります。
    
- 別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。
    

