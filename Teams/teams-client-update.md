---
title: チームの更新
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Teams デスクトップクライアントの更新方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba6201d0f1b52b7ebfd869ad699c2eb06eb664d8
ms.sourcegitcommit: 0d7f3c7a84584ec25a23190187215109c8756189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37508802"
---
# <a name="teams-update-process"></a>Teams の更新プロセス

Teams web app が毎週更新されます。

Teams のデスクトップクライアントの更新プログラムは、skype の技術導入プログラムを通じて、社内の厳密なテストと検証の2週間ごとにリリースされます (タップ)。 通常、これは火曜日で行われます。 重要な更新が必要な場合は、チームはこのスケジュールを無視し、利用可能になったらすぐに更新プログラムをリリースします。

デスクトップクライアントは自動的に更新されます。 チームは、バックグラウンドで数時間ごとに更新プログラムを確認し、それをダウンロードした後、更新プログラムをサイレントインストールする前にコンピューターがアイドル状態になるまで待機します。

ユーザーは、アプリの右上にある [**プロファイル**] ドロップダウンメニューの [**更新プログラムの確認**] をクリックして、手動で更新プログラムをダウンロードすることもできます。 更新プログラムが利用可能な場合は、コンピューターがアイドル状態になったときにダウンロードされ、黙ってインストールされます。

更新プログラムをダウンロードするには、ユーザーがサインインしている必要があります。 

2019年7月31日から、Teams クライアントの更新では、更新中にネットワーク帯域幅が大幅に減少します。 これは既定でオンになっており、管理者またはユーザーが操作する必要はありません。

## <a name="what-about-updates-to-office-365-proplus"></a>Office 365 ProPlus の更新プログラムについて

Office は既定で、office 365 ProPlus の新しいインストールと共にインストールされます。詳しくは、「 [office 365 で Microsoft Teams を展開する ProPlus](https://docs.microsoft.com/DeployOffice/teams-install)」を参照してください。 

チームは、前に説明したように、独自の更新プロセスに従いますが、Word や Excel など、他のオフィスアプリの更新プロセスではありません。 詳細については、「 [Office 365 ProPlus の更新プログラムチャネルの概要」](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)を参照してください。

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI でのチームの更新について

仮想デスクトップインフラストラクチャ (VDI) 上の Teams クライアントは、非 VDI Teams クライアントのように自動的には更新されません。 「Team を[VDI にインストール](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)する」の手順に従って、新しい MSI をインストールして、VM イメージを更新する必要があります。 最新バージョンに更新するには、現在のバージョンをアンインストールする必要があります。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>管理者がチームの自動更新の代わりに更新プログラムを展開することはできますか?

チームは、任意の配信メカニズムを使用して更新プログラムを展開する権限を管理者に付与することはできません。

## <a name="servicing-agreement"></a>サービス契約

最新のオンラインサービスとして、Teams クライアントは2週間ごとに自動更新されます。 Teams は最新のライフサイクルポリシーによって管理されるため、ユーザーは最新バージョンのデスクトップクライアントを維持している必要があります。 これにより、ユーザーは最新の機能、パフォーマンスの拡張、セキュリティ、およびサービスの信頼性を確保することができます。

デスクトップクライアントが最新の状態になっているかどうかを特定するための支援を始めるには、ユーザーの現在のバージョンが 1 ~ 3 か月前であり、新しいバージョンが利用可能であるかどうかをアプリ内通知で確認します。 このアプリ内のメッセージは、ユーザーが最新バージョンの Teams に更新したり、必要に応じて IT 管理者に連絡したりすることを促します。 3ヶ月以上前の Teams デスクトップクライアントのユーザーには、今すぐ更新、IT 管理者への連絡、web 上のチームへの参加などのオプションを提供するブロックページが表示されます。

初めてインストールしたときから3ヶ月以上経過したデスクトップクライアントのバージョンについては、上記のサービス情報に遭遇する前に、28日間の猶予期間が含まれています。 この期間中、自動更新プロセスによって Teams クライアントが更新されます。 更新されていない場合は、最新バージョンの Teams に手動で更新するか、必要に応じて IT 管理者に連絡するために、アプリ内警告が表示されます。 これには、Office 365 ProPlus バンドルの一部として Teams デスクトップクライアントを使用するユーザーも含まれます。

政府機関向けの Teams デスクトップクライアントには、現時点で通知が表示されるまで、現在このサービス契約には例外があります。

新しいバージョンのリリースについては[、メッセージセンター](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)を確認**するか** > 、「クライアントの**新機能**」を参照してください。
