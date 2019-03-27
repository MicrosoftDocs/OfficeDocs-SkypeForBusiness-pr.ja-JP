---
title: (省略可能)ビジネス用の Skype のコール パーク展開を確認します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: ビジネス サーバーのエンタープライズ VoIP の Skype のコール パークの展開を確認しています。
ms.openlocfilehash: 514c82590d56a2de16ca31cc892032afe5e7a34c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895098"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(省略可能)ビジネス用の Skype のコール パーク展開を確認します。
 
ビジネス サーバーのエンタープライズ VoIP の Skype のコール パークの展開を確認しています。 
  
インストールし、コール パークを構成した後は、駐車場との呼び出しを取得するが、期待どおりに動作するかどうかを確認する構成を確認する必要があります。 少なくとも、以下を確認してください。
  
- コール パークを有効になっているを持つユーザーを呼び出すし、ユーザーの公園の呼び出しがあります。
    
    > [!NOTE]
    > 音声ポリシーでコール パークを有効に、このテストを実行する前に、ビジネス用の Skype からサインアウトして、再度サインイン、通話リストの転送では、コール パーク オプションを表示することができるようにする呼び出しは、駐車場ユーザー必要があります。 
  
- オービット番号をダイヤルして、電話を取ります。
    
- 別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。
    

