---
title: Skype for Business Server 2015 でのアナウンス アプリケーションの展開プロセス
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 展開プロセスとビジネス サーバーのエンタープライズ VoIP は、Skype で知らせアプリケーションの手順を実行します。
ms.openlocfilehash: 08a52569dede43bbe54b1bf7e62f37114ba68853
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのアナウンス アプリケーションの展開プロセス
 
展開プロセスとビジネス サーバーのエンタープライズ VoIP は、Skype で知らせアプリケーションの手順を実行します。
  
アナウンス アプリケーションは、割り当てられていない拡張機能 (拡張機能、組織に有効ですが、ユーザーや電話に割り当てられていない) への呼び出しの動作を構成することを可能にするエンタープライズ VoIP 機能です。 たとえば、割り当てられていない番号に通話があった場合にメッセージを再生したり、別の通話先に転送したり、その両方を行ったりするように構成できます。
  
エンタープライズ VoIP を展開する場合、フロント エンド サーバーまたは Standard Edition サーバー上の応答グループ アプリケーションの機能としてお知らせアプリケーションをインストールするとします。 オーディオ ファイルをアップロードするか音声合成 (TTS) を構成して、割り当てられていない番号の表を構成し、アナウンスを構成する必要があります。
  
ここでは、アナウンス アプリケーションの展開に必要な手順の概要を示します。 アナウンスを構成する前に、エンタープライズ VoIP を展開する必要があります。 アナウンス アプリケーションで必要なコンポーネントでは、インストールされ、エンタープライズ VoIP を展開するときに有効にすることがします。
  
**アナウンスの展開プロセス**

|**フェーズ**|**手順**|**ロール**|**展開に関するドキュメント**|
|:-----|:-----|:-----|:-----|
|アナウンス設定の構成  <br/> | オーディオ ファイルをレコーディングして読み込むか、音声合成 (TTS) を使用して、アナウンスを作成します。 <br/>  割り当てられていない番号の表で、割り当てられていない番号の範囲を構成して、適切なアナウンスに関連付けます。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[ビジネス サーバー 2015 の Skype でお知らせを削除をします。](create-an-announcement.md) <br/> [作成またはビジネス サーバー 2015 の Skype に割り当てられていない番号の範囲を変更します。](create-or-modify-an-unassigned-number-range.md) <br/> |
|アナウンスの展開の確認  <br/> |アナウンスを聞いてテストし、構成が予想どおりに動作することを確認します。  <br/> |-  <br/> |[(省略可能)ビジネス 2015年の Skype で知らせの展開を確認します。](optional-verify-announcement-deployment.md) <br/> |
   

