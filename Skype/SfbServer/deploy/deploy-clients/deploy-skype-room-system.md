---
title: Skype ルーム システムの展開の概要
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
description: 方法については、Skype ルーム システムでは、会議を導入してルーム ソリューションの統合されたハードウェアと Skype をビジネス ・ ミーティングに参加するのには最適なソフトウェアで構成されます。
ms.openlocfilehash: 94a9b1cb7ff3f341a51944cdc678bc66e44831cb
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699318"
---
# <a name="deployment-planning-for-skype-room-system-in-skype-for-business"></a>ビジネス用の Skype の Skype ルームのシステムの計画の展開
 
方法については、Skype ルーム システムでは、会議を導入してルーム ソリューションの統合されたハードウェアと Skype をビジネス ・ ミーティングに参加するのには最適なソフトウェアで構成されます。
  
> [!NOTE]
> これの目的でコンテンツ、Crestron RL、スマート ・ ルーム システムのビジネス用の Skype とポリコム CX8000 があると呼ばれる Skype ルーム システムです。 

> [!NOTE]
> Skype ルーム システム v2 は、さまざまな依存関係および展開の手順で別の製品です。 Skype ルーム システム v2 については、 [Skype ルーム システムの計画のバージョン 2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)を参照してください。
  
 Skype ルーム システムは、Skype のビジネス会議は、物理的な会議室での最適化された統合コミュニケーション クライアントをビジネス用の Skype です。
  
Skype ルーム システムのクライアントは、ビジネスの SDK は、Skype を使用してビジネス クライアント用の Skype から開発されました。 ビジネス クライアント用の Skype は、一部の UI が非表示モードでバック グラウンドで実行されます。 ビジネス クライアント用の Skype では、ビデオ ギャラリー、部屋の前面にある画面上のコンテンツのステージを制御します。 Skype ルーム システムのクライアントは、会議を制御するため、卓上型のディスプレイにコンソール経験を提供します。 Skype ルームのシステムを提供します。 
  
- ワンタッチでの会議への参加
    
- マルチビュー ビデオ ギャラリーの自動セットアップ 
    
- 会議室の前方画面でのタッチ対応ホワイトボード 
    
- スケジュールされた会議にアクセスできるカレンダー統合
    
- コンテンツの共有と切り替え 
    
このガイドでは、ビジネスのサーバーと Exchange Server の Skype の Skype ルームのシステムをプロビジョニングします。 管理者は、会議室でアプライアンスの PC とデバイスの設定の手順が用意されている Skype ルーム システムのインストール ガイドを参照してください。 
  
## <a name="prerequisites"></a>必要条件

Skype ルーム システムの要件は、以下です。 
  
- Exchange リソース メールボックス アカウント。Exchange Server (できれば 2013) で有効になっている AutoDiscover サービスを使用する会議室で予定表によるスケジューリングをやりやすくするためです。
    
- ビジネス サーバー プール (エンタープライズまたは Standard Edition) は、Skype の Skype ルーム システムのビジネスを有効にしたアカウントの Skype です。
    
- 必要なすべてのソフトウェアがインストールされた Skype ルーム システム クライアント アプライアンス PC です。 アプライアンス PC では Windows 7 Embedded Standard オペレーティング システムが実行されていることが必要です。 アプライアンス PC は、機器一式 (ディスプレイ、カメラ、マイク、スピーカー) と併せて OEM パートナーから提供されます。
    
- PC Skype ルーム システムのアプライアンスを Active Directory ドメイン サービス (AD DS) ドメインに参加させる場合は、Skype の部屋のシステムに影響を与えないグループ ポリシーの設定を指定する必要があります。 また、アプライアンス PC を Workgroup のままにしておくこともできます。 
    
- この記事で指示されているコマンドレットを実行するための適切なユーザー権限。CsMeetingRoom コマンドレットは CsUser コマンドレットを基にモデル化されています。そのため、CsUser コマンドレットを実行するために必要な役割ベースのアクセス制御 (RBAC) の役割がすべて、CsMeetingRoom コマンドレットを実行するためにも必要です。 
    
## <a name="supported-topologies"></a>サポートされるトポロジ

Skype ルーム システム クライアント、社内設置型またはクラウドで、ビジネスおよび Exchange のトポロジの Skype のさまざまな環境間での相互運用性を次の表に示します。 
  

|**トポロジ**|**AD**|**Skype for Business**|**交換**|
|:-----|:-----|:-----|:-----|
|オンプレミス  <br/> |オンプレミス  <br/> |オンプレミス  <br/> |オンプレミス  <br/> |
|Office 365 のマルチ テナント型 (O365MT)  <br/> |オンライン  <br/> |オンライン  <br/> |オンライン  <br/> |
|Office 365 専用  <br/> (サービス プロバイダーに問い合わせてください)  <br/> |オンプレミス  <br/> |オンライン  <br/> |オンライン  <br/> |
|ハイブリッド (分割ドメイン)  <br/> 未サポート  <br/> |オンプレミス  <br/> オンプレミス  <br/> オンプレミス  <br/> |オンプレミス  <br/> オンライン  <br/> オンライン  <br/> |オンライン  <br/> オンライン  <br/> オンプレミス  <br/> |
   
Lync Server 2013 より前のリリースは、部分的にサポートします。 これらのシナリオで Skype ルームのシステムに参加できる Skype (ユーザーによってスケジュールされたものが置かれている Lync Server 2010) ビジネス会議の会議は、"public"は、限り、会議の意味は用にカスタマイズされたアクセスを制限します。 
  
Skype ルーム システムは、Lync server のバージョンの Lync Server 2013 より前のホームことはできません。 Skype ルーム システムは、カレンダーの設定 - を取得するために Exchange に接続できない場合など、Skype ルーム システム アカウント用に構成された Exchange メールボックスがないか、Exchange にアクセスすることはできません--とアドホック会議と会議の開始が、参加するが、スケジュールされた会議は表示されません。 
  
次の表は、Exchange Server のバージョンと Skype ルーム システム クライアントのサポートを示します。 
  

|**交換**|**オンプレミス**|**オンライン**|**ハイブリッド**|
|:-----|:-----|:-----|:-----|
|Exchange 2010  <br/> |はい (単一フォレストのみ)  <br/> |該当なし  <br/> |該当なし  <br/> |
|Exchange 2013  <br/> |はい (複数フォレスト サポートは Exchange 2013 CU6 以降のバージョン)  <br/> |可  <br/> |あり  <br/> |
|Exchange 2016  <br/> |[はい] (複数フォレストのサポート可能)  <br/> |あり  <br/> |はい  <br/> |
   

