---
title: Skype for Business Server のアナウンスメントアプリケーションの展開プロセス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Skype for Business Server Enterprise Voice の展開プロセスとお知らせアプリケーションの手順。
ms.openlocfilehash: 77d15c4ce749a97ec11ed5d5e083ccf6fa2aecfa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275609"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Skype for Business Server のアナウンスメントアプリケーションの展開プロセス
 
Skype for Business Server Enterprise Voice の展開プロセスとお知らせアプリケーションの手順。
  
アナウンスメントアプリケーションは、割り当てられていない拡張子 (組織に対して有効であり、ユーザーまたは電話に割り当てられていない拡張機能) への呼び出しを構成できるエンタープライズ Voip 機能です。 たとえば、割り当てられていない番号に通話があった場合にメッセージを再生したり、別の通話先に転送したり、その両方を行ったりするように構成できます。
  
お知らせアプリケーションは、エンタープライズボイスの展開時に、フロントエンドサーバーまたは Standard Edition サーバー上の応答グループアプリケーションの機能としてインストールされます。 オーディオ ファイルをアップロードするか音声合成 (TTS) を構成して、割り当てられていない番号の表を構成し、アナウンスを構成する必要があります。
  
このセクションでは、アナウンスメントアプリケーションの展開に関連する手順の概要を説明します。 お知らせを構成する前に、エンタープライズボイスを展開する必要があります。 [エンタープライズ Voip] を展開すると、アナウンスメントアプリケーションで必要なコンポーネントがインストールされて有効になります。
  
**アナウンスの展開プロセス**

|**段階**|**手順**|**Roles**|**「展開」のドキュメント**|
|:-----|:-----|:-----|:-----|
|アナウンス設定の構成  <br/> | オーディオ ファイルをレコーディングして読み込むか、音声合成 (TTS) を使用して、アナウンスを作成します。 <br/>  割り当てられていない番号の表で、割り当てられていない番号の範囲を構成して、適切なアナウンスに関連付けます。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Skype for Business Server でお知らせを作成または削除する](create-an-announcement.md) <br/> [Skype for Business Server で割り当てられていない番号範囲を作成または変更する](create-or-modify-an-unassigned-number-range.md) <br/> |
|アナウンスの展開の確認  <br/> |アナウンスを聞いてテストし、構成が予想どおりに動作することを確認します。  <br/> |-  <br/> |[省略Skype for Business でのアナウンスメントの展開を確認する](optional-verify-announcement-deployment.md) <br/> |
   

