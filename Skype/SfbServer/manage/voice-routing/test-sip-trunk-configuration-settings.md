---
title: Skype のビジネス サーバーの SIP トランクの構成設定をテストします。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP トランクの構成設定は、仲介サーバーおよび公衆交換電話網 (PSTN) ゲートウェイ、IP 公開ブランチ交換機 (PBX)、またはサービス プロバイダーのセッション ボーダー コント ローラー (SBC) の間での機能との関係を定義します。 '
ms.openlocfilehash: 3f251ea720ab220ccda0cfe9882d4a8396085aa0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214625"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="f1b0b-103">Skype のビジネス サーバーの SIP トランクの構成設定をテストします。</span><span class="sxs-lookup"><span data-stu-id="f1b0b-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="f1b0b-104">SIP トランクの構成設定は、仲介サーバーおよび公衆交換電話網 (PSTN) ゲートウェイ、IP 公開ブランチ交換機 (PBX)、またはサービス プロバイダーのセッション ボーダー コント ローラー (SBC) の間での機能との関係を定義します。</span><span class="sxs-lookup"><span data-stu-id="f1b0b-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="f1b0b-105">たとえば、次の設定ができます。</span><span class="sxs-lookup"><span data-stu-id="f1b0b-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="f1b0b-106">トランクでメディア バイパスを有効化するか。</span><span class="sxs-lookup"><span data-stu-id="f1b0b-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="f1b0b-107">リアルタイム転送制御プロトコル (RTCP) パケットを送信する条件です。</span><span class="sxs-lookup"><span data-stu-id="f1b0b-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="f1b0b-108">かどうか各トランクには、セキュリティで保護されたリアルタイム プロトコル (SRTP) 暗号化が必要です。</span><span class="sxs-lookup"><span data-stu-id="f1b0b-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="f1b0b-109">ビジネス サーバーの Skype をインストールすると SIP トランク構成設定のグローバル コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f1b0b-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="f1b0b-110">また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f1b0b-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="f1b0b-111">管理者は、トランクがゲートウェイによって処理できる数をユーザーがダイヤルした番号を変換できることを確認するのには[テスト CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration)コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1b0b-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="f1b0b-112">トランク構成設定は、Windows PowerShell と Test-CsTrunkConfiguration コマンドレットを使用する方法でのみテストできます。</span><span class="sxs-lookup"><span data-stu-id="f1b0b-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="f1b0b-113">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1b0b-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="f1b0b-114">**SIP トランク構成設定をテストするには**</span><span class="sxs-lookup"><span data-stu-id="f1b0b-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="f1b0b-115">このコマンドを実行すると、ダイヤルされた番号 4255551212 がレドモンド サイトのトランク構成設定によって正しく変換できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f1b0b-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
