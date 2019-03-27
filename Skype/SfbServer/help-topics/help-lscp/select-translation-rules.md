---
title: 変換ルールの選択
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: エンタープライズ VoIP では、すべてのダイヤル文字列が番号の逆引き参照 (RNL) を実行するための E.164 形式に正規化する必要があります。 一方、トランク ピア (つまり、関連付けられたゲートウェイ、PBX、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。 E.164 形式から地域のダイヤル形式に番号を変換するには、オプションとして、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。
ms.openlocfilehash: 0dd2a50f68423a502fb25ba194ab82de76d356d7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891323"
---
# <a name="select-translation-rules"></a>変換ルールの選択
 
 エンタープライズ VoIP では、すべてのダイヤル文字列が番号の逆引き参照 (RNL) を実行するための E.164 形式に正規化する必要があります。 一方、トランク ピア (つまり、関連付けられたゲートウェイ、PBX、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。 E.164 形式から地域のダイヤル形式に番号を変換するには、オプションとして、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。
  
> [!IMPORTANT]
> トランク ピアで変換ルールを構成する代わりに使用するものでは 1 つまたは複数の変換ルールをエンタープライズ VoIP のトランク構成に関連付けること。 2 つのルールが競合する可能性がありますので、トランク ピアで変換ルールを構成している場合は、エンタープライズ VoIP のトランク構成の変換規則を関連付けないでください。 
  
既存の変換ルールを使用するには、一覧でルールをクリックして [**OK**] をクリックします。
  
詳細ビジネス サーバーのコントロール パネルの Skype を使用して実行できるさまざまな手順については、[ビジネス サーバー 2015 の Skype の管理](../../manage/manage.md)を参照してください。
  

