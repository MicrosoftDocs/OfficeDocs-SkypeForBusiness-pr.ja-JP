---
title: Lync Server 2010 用のエッジ サーバー FQDN 設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: '[外部設定] のプロパティを定義するには、次のように構成します。'
ms.openlocfilehash: 6b833e89a8e1288af9a203dd5f44201c253ff2f9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282599"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用のエッジ サーバー FQDN 設定エキスパンダー
 
[**外部設定**] のプロパティを定義するには、次のように構成します。
  
Web 会議や音声/ビデオ用のプールの FQDN と IP アドレスを個別に定義する場合は、[ **web 会議と ip アドレスを別々に使用**する] チェックボックスをオンにします。
  
> [!NOTE]
> 独立した FQDN と IP アドレスのチェックボックスをオンにしない場合は、エッジサーバーによって提供される3つのサービスごとに個別のポートを指定する必要があります。 構成する完全修飾ドメイン名は、アクセスエッジサービスに関連付けられている FQDN です。 
  
A/v Edge サービスでネットワークアドレス変換 (NAT) IP アドレスと構成を使用する場合は、[ **a/v edge サービスは nat を有効**にする] チェックボックスをオンにします。
  
有効なエッジサービスの場合、[**ポート**] に**プールの FQDN**とポートを入力します。
  
- **アクセスエッジサービス**プールの FQDN と、サービスを一意に識別するポートを定義します。
    
- **Web 会議エッジサービス**プールの FQDN を定義します ([web 会議用に個別の FQDN と IP アドレスを有効にし、A/V が選択されていない場合)。また、サービスを一意に識別するポート。
    
- **A/v Edge サービス**プールの FQDN を定義します ([web 会議のために別々の FQDN と IP アドレスを有効にし、a/v が選択されていない場合)。また、サービスを一意に識別するポート。
    
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

