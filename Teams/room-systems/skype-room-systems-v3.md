---
title: Microsoft Teams のルームの管理の概要
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Microsoft Teams のルームの管理の概要。
ms.openlocfilehash: 01b2550c1a0ad691acf48c58f6c13a37f2b4b7e6
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2019
ms.locfileid: "35198637"
---
# <a name="management-overview"></a>管理の概要 

Microsoft Teams の部屋システムがユーザーに提供され、優れたユーザーエクスペリエンスを提供できるように、継続的なメンテナンスと運用を開発して実施することが重要です。 

## <a name="monitoring"></a>監視 

Microsoft Teams のルームシステムの監視は、次の2つの主要なアクティビティで構成されます。

-  デバイス、アプリケーション、周辺機器の監視

-  品質と信頼性の監視 (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Microsoft Teams の会議室デバイス、アプリケーション、周辺機器の監視

ユーザーが Microsoft Teams のルームユニットを使用できるようにするには、単位をオンにして、Microsoft Teams のルームアプリケーションで正しく構成されたネットワークに接続して、機能している周辺デバイスに接続する必要があります。 


Microsoft Teams のルームアプリケーションと接続されている周辺機器の状態に関する情報は、Microsoft Teams のルームアプリケーションによって Windows イベントログに書き込まれ、[ログエントリを理解](azure-monitor-manage.md#understand-the-log-entries)するために文書化されています。 

|**]**|**よう**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |Microsoft Teams のルームを起動できるようにします。  <br/> |
|電源管理-\> AC 電源、10分後に画面をオフにする  <br/> 電源管理-\> AC で、システムをスリープ状態にしない  <br/> |Microsoft Teams の会議機能を有効にして、添付されたディスプレイをオフにし、自動的にスリープ状態を解除する  <br/> |
|net accounts /maxpwage:unlimited  <br/> または、ローカルアカウントのパスワードの有効期限を無効にすることもできます。 そうしないと、有効期限が切れたパスワードについて、Skype アカウントがログオンに失敗することになります。 これは、マシン上のすべてのローカルアカウントに影響を与えるため、これを設定しないと、そのボックスの管理者アカウントも最終的に有効期限切れになります。  <br/> |常にログインするように Skype アカウントを有効にする  <br/> |
   
グループポリシーを使用してファイルを転送する方法については[、「ファイルを構成](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)する」をお勧めします。
  
## <a name="remote-management-using-powershell"></a>PowerShell を使用したリモート管理
<a name="RemotePS"> </a>

Microsoft Operations Manager スイートを使用して、Microsoft Teams のルームシステムを監視することをお勧めします。 監視と基本的な通知の設定方法のガイダンスについては、「 [Azure モニターを使用して Microsoft Teams のルーム管理を展開](azure-monitor-deploy.md)する」を参照してください。 

このガイダンスを使用すると、簡単に使用できるダッシュボードを作成して、Microsoft Teams のルーム単位での展開の問題を特定することができます。 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>判断のポイント|<ul><li>Operations Management Suite を使用して、Microsoft Teams ルームの展開を監視することを確認します。</li><li>メール通知に使用するターゲット配布リストを決定します。</li></ul>|
|![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>品質と信頼性の監視方法を定義します。</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>品質と信頼性の監視 (CQD)

現在の運用品質と信頼性の監視手順は展開の一部として実装することをお勧めします。通話と品質と信頼性のトレンドを監視し、問題の領域を特定し、解決に向けて作業することをお勧めします。 

CQD に建物情報をアップロードする場合は、建物レベルで通話品質と信頼性の傾向を調べることができます。これにより、建物を比較したり、特定の問題に注意を向けることが簡単になります。

品質と信頼性の傾向を特定し[](https://aka.ms/qerguide) 、問題を解決するためのアクションプランを作成することをお勧めします。 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>Microsoft Teams のルーム OS および Microsoft Teams のルームアプリケーションを更新する

Microsoft Teams 室の OS および Microsoft Teams のルームアプリケーションを更新して、製品の更新や改善を活用することをお勧めします。 詳細なガイドについては、「 [Microsoft Teams のルームを管理](room-systems-v2-operations.md#software-updates)する」を参照してください。 

## <a name="windows-updates"></a>Windows の更新プログラム

Microsoft Teams の会議は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップと同じ Windows 更新プログラムと OS ビルドを受け取ります。 詳細については、「 [Windows 更新プログラムを管理](updates.md)する」をご覧ください。


## <a name="troubleshooting"></a>トラブルシューティング

上のセクションで説明されているように、operations Management Suite 通知を設定することをお勧めします。これにより、運用チームとヘルプデスクは Microsoft Teams の会議の問題について通知されます。 PowerShell リモート管理のオプションについては、「 [powershell を使用したリモート管理](room-systems-v2-operations.md#remote-management-using-powershell)」を参照してください。 周辺機器が切断されている場合は、ローカルの "スマートハンド" または IT サポートに依存して、デバイスを調査し、再接続することが必要な場合があります。 

トラブルシューティングと管理モードの詳細については、「 [Microsoft Teams のルームを管理](room-systems-v2-operations.md#admin-mode-and-device-management)する」を参照してください。 


## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams のルームを計画する](skype-room-systems-v2-0.md)

[Microsoft Teams ルームの展開](room-systems-v2.md)

[Microsoft Teams 室コンソールを構成する](console.md)

[XML 構成ファイルを使用して、Microsoft Teams ルームコンソールの設定をリモートで管理する](xml-config-file.md)
