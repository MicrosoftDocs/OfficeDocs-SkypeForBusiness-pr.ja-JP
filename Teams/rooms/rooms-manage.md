---
title: Microsoft Teams ミーティングの管理の概要
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Microsoft Teams のルームシステムがユーザーに対して利用可能になるように、継続的なメンテナンスと運用を開発して実行する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6b63e42e1f3fa3d5540936d562aa913837103ed1
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905369"
---
# <a name="management-overview"></a>管理の概要

Microsoft Teams の部屋システムがユーザーに提供され、優れたユーザーエクスペリエンスを提供できるように、継続的なメンテナンスと運用を開発して実施することが重要です。 

## <a name="monitoring"></a>監視 

Microsoft Teams ミーティング システムの監視は、次の 2 つの主要なアクティビティで構成されます。

- デバイス、アプリケーション、周辺機器の監視
- 品質と信頼性の監視 (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Microsoft Teams ミーティング デバイス、アプリケーション、周辺機器の監視

Microsoft Teams ミーティングのユニットをユーザーが使えるようにするには、ユニットの電源を入れ、Microsoft Teams ミーティング アプリケーションを正しく構成したうえでネットワークに接続し、正常に機能している周辺機器に接続する必要があります。 

Microsoft Teams ミーティング アプリケーションと接続している周辺機器の状態についての情報は、Microsoft Teams ミーティング アプリケーションによって Windows イベント ログに書き込まれ、[ログ エントリーを理解する](azure-monitor-manage.md#understand-the-log-entries)ために文書化されています。 

|**設定**|**許可**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |Microsoft Teams ミーティングの起動を有効にする  <br/> |
|電源管理 -\> AC で、10 分後に画面をオフにする  <br/> 電源管理 -\> AC で、システムをスリープさせない  <br/> |接続されているディスプレイをオフにし、自動的にウェイク アップさせるように Microsoft Teams ミーティングを有効化する  <br/> |
|net accounts /maxpwage:unlimited  <br/> これは、ローカル アカウントでパスワードの有効期限を無効にすることに相当します。 この操作を行わないと、最終的に Skype アカウントがログオンできなくなり、パスワードの有効期限が切れているという通知が発生します。 これは、コンピューター上のすべてのローカル アカウントに影響を与えるため、設定に失敗すると、ボックスの管理者アカウントも最終的に有効期限切れになります。  <br/> |常にログインするように Skype アカウントを有効にする  <br/> |

グループ ポリシーを使用してファイルを転送する方法については、「[ファイルの項目を構成する](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)」で説明しています。
  
## <a name="remote-management-using-powershell"></a>PowerShell を使ったリモート管理
<a name="RemotePS"> </a>

Microsoft Operations Manager Suite を使用して、Microsoft Teams ミーティング システムを監視することをお勧めします。 監視と基本的な通知を設定する方法についてのガイダンスは、「[Azure Monitor で Microsoft Teams ミーティングの管理を展開する](azure-monitor-deploy.md)」を参照してください。 

このガイダンスを使って、簡単に使えるダッシュボードを作り、展開における Microsoft Teams ミーティングのユニットに関する問題点を特定することができます。 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Operations Management Suite を使って Microsoft Teams ミーティングの展開を監視することを確認します。</li><li>メール通知に使用するターゲット配布リストを決定します。</li></ul>|
|![](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>品質と信頼性の監視アプローチを定義します。</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>品質と信頼性の監視 (CQD)

通話と会議の品質および信頼性の傾向を監視する展開の一環として、運用上の品質および信頼性に対する継続的な監視の手順を実行することにより、懸念のある部分を特定し、解決に向けて取り組むようにお勧めします。 

CQD に建物の情報をアップロードすると、建物の階ごとに通話の品質と信頼性の傾向を調査することができ、これにより建物間で比較したり、特定の問題に注目したりしやすくなります。

[QoE のレビュー ガイド](https://aka.ms/qerguide)を確認して従うことにより、品質と信頼性の傾向を特定し、解決へ向けて行動計画を立てるようお勧めします。 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>Microsoft Teams ミーティング OS と Microsoft Teams ミーティング アプリケーションの更新

Microsoft Teams ミーティング OS と Microsoft Teams ミーティング アプリケーションを更新して、製品の更新プログラムや機能強化を活用するようお勧めします。 詳細なガイダンスについては、「[Microsoft Teams ミーティングを管理する](rooms-operations.md#software-updates)」を参照してください。 

## <a name="windows-updates"></a>Windows の更新プログラム

Microsoft Teams ミーティングは Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で動作し、同じ Windows の更新プログラムと OS ビルドを標準デスクトップとして受け取ります。 詳細については、「[Windows 更新プログラムを管理する](updates.md)」を参照してください。


## <a name="troubleshooting"></a>トラブルシューティング

上記のセクションで前述したように、Operations Management Suite の通知を設定し、Microsoft Teams ミーティングの問題についての通知をお客様の運用チームやヘルプデスクが受け取れるようにすることをお勧めします。 PowerShell リモート管理用のオプションについては、「[PowerShell を使ったリモート管理](rooms-operations.md#remote-management-using-powershell)」を参照してください。 周辺機器が切断されている場合は、ローカルの "スマートハンド" または IT サポートに依存して、デバイスを調査し、再接続することが必要な場合があります。 

トラブルシューティングと管理モードについての詳細は、「[管理者モードとデバイス管理](rooms-operations.md#admin-mode-and-device-management)」を参照してください。 


## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams ミーティングを計画する](rooms-plan.md)

[Microsoft Teams ミーティングを展開する](rooms-deploy.md)

[Microsoft Teams ミーティングのコンソールを構成する](console.md)

[Microsoft Teams ミーティング のコンソールの設定を、XML 構成ファイルを使用してリモートで管理する](xml-config-file.md)
