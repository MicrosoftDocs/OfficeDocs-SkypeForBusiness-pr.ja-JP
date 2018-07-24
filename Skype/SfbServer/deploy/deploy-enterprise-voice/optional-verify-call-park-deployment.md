---
title: (省略可能)ビジネス用の Skype のコール パーク展開を確認します。
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
ms.openlocfilehash: b07b3b3bfb709770a4f30f2f6cb43e5ce5dbcc3a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000530"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(省略可能)ビジネス用の Skype のコール パーク展開を確認します。
 
ビジネス サーバーのエンタープライズ VoIP の Skype のコール パークの展開を確認しています。 
  
インストールし、コール パークを構成した後は、駐車場との呼び出しを取得するが、期待どおりに動作するかどうかを確認する構成を確認する必要があります。 少なくとも、以下を確認してください。
  
- コール パークを有効になっているを持つユーザーを呼び出すし、ユーザーの公園の呼び出しがあります。
    
    > [!NOTE]
    > 音声ポリシーでコール パークを有効に、このテストを実行する前に、ビジネス用の Skype からサインアウトして、再度サインイン、通話リストの転送では、コール パーク オプションを表示することができるようにする呼び出しは、駐車場ユーザー必要があります。 
  
- オービット番号をダイヤルして、電話を取ります。
    
- 別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。
    

