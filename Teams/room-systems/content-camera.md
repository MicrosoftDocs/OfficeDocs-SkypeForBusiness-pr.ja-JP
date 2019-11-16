---
title: XML 構成ファイルを使用して、Microsoft Teams ルームコンソールの設定をリモートで管理する
ms.author: serdars
author: serdarsoysal
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: この記事では、Microsoft Teams のルームデバイスで使用される既定の設定をリモート管理する方法について説明します。カスタムテーマの適用を含みます。
ms.openlocfilehash: 21f60c95c556e9fd006d378a0ff7b48dd0b1b6c2
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675765"
---
# <a name="content-cameras"></a><span data-ttu-id="1269c-103">コンテンツ カメラ</span><span class="sxs-lookup"><span data-stu-id="1269c-103">Content cameras</span></span>

<span data-ttu-id="1269c-104">Microsoft Teams Room system でコンテンツカメラを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1269c-104">You can now use a content camera with a Microsoft Teams Room system.</span></span> <span data-ttu-id="1269c-105">コンテンツのカメラは、特殊な画像処理ソフトウェアやホワイトボードと連携し、発表者がアナログホワイトボードを描画し、リモート参加者とコンテンツを共有できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1269c-105">A content camera interacts with special image-processing software and a whiteboard to allow a presenter to draw on an analog whiteboard and share the content with remote participants.</span></span>

<span data-ttu-id="1269c-106">コンテンツのカメラ機能の例については、次のビデオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1269c-106">See the following video for examples of content camera functionality.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a><span data-ttu-id="1269c-107">コンテンツのカメラを設定する</span><span class="sxs-lookup"><span data-stu-id="1269c-107">Set up a content camera</span></span>

> [!NOTE]
> <span data-ttu-id="1269c-108">常に、お住まいの国または地域の建物コードに準拠します。これにより、床からの距離を最小限にすることができます。また、rafter やその他の構造体に固定されている機器を保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1269c-108">Always adhere to your country or area's building code, which may define a minimum distance from the floor or a requirement that ceiling-mounted equipment be secured to a rafter or other structure.</span></span> <span data-ttu-id="1269c-109">選択したカメラに同梱されているハードウェアの装着手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1269c-109">Follow the mounting instruction for the hardware provided with the camera you‘ve selected.</span></span> <span data-ttu-id="1269c-110">OEM カメラの取り付けキットには、カメラ、USB 2.0 エクステンダー、および必要なケーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1269c-110">OEM camera mounting kits include a camera, USB 2.0 extenders and required cabling.</span></span>

<span data-ttu-id="1269c-111">共有に使用するホワイトボードのサイズは、カメラの位置に影響します。</span><span class="sxs-lookup"><span data-stu-id="1269c-111">The size of the whiteboard used for sharing affects the placement of the camera.</span></span> <span data-ttu-id="1269c-112">ボードサイズの推奨事項:</span><span class="sxs-lookup"><span data-stu-id="1269c-112">Board size recommendations are:</span></span>

- <span data-ttu-id="1269c-113">3 ~ 6 フィート (0.9 ~ 1.8 m)、サポートされています</span><span class="sxs-lookup"><span data-stu-id="1269c-113">3–6 ft. (0.9–1.8 m) wide — Supported</span></span>
- <span data-ttu-id="1269c-114">6 ~ 9 フィート (1.8 ~ 2.7 m)、お勧め</span><span class="sxs-lookup"><span data-stu-id="1269c-114">6–9 ft. (1.8–2.7 m) wide — Recommended</span></span>
- <span data-ttu-id="1269c-115">9 ~ 12 フィート (2.7 ~ 3.6 m)、サポートされています</span><span class="sxs-lookup"><span data-stu-id="1269c-115">9–12 ft. (2.7–3.6 m) wide — Supported</span></span>
- <span data-ttu-id="1269c-116">12フィート (3.6 m) 以上の幅-カメラカバー 9 ~ 12 フィート (2.7 ~ 3.6 m) と残りのトリミング。</span><span class="sxs-lookup"><span data-stu-id="1269c-116">Above 12 ft. (3.6 m) wide — camera covers 9–12 ft. (2.7–3.6 m) and crops the rest.</span></span>

## <a name="camera-location"></a><span data-ttu-id="1269c-117">カメラの場所</span><span class="sxs-lookup"><span data-stu-id="1269c-117">Camera location</span></span>

<span data-ttu-id="1269c-118">コンテンツカメラの最適な配置は、ホワイトボード上で垂直方向と水平方向に配置されています。</span><span class="sxs-lookup"><span data-stu-id="1269c-118">Ideal placement of a content camera is centered vertically and horizontally on the whiteboard.</span></span> <span data-ttu-id="1269c-119">ローカルの建物コードには、画面上の余白を超える高さの制約がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1269c-119">Local building codes may have height restrictions that require the camera be elevated higher than the top of the white board.</span></span>

<span data-ttu-id="1269c-120">最大6つのカメラをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="1269c-120">You can install the camera up to 6 in.</span></span> <span data-ttu-id="1269c-121">(152 mm) ホワイトボードの上部よりも大きく、ホワイトボードの中央にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="1269c-121">(152 mm) higher than the top of the whiteboard, and centered on the white board as shown.</span></span> <span data-ttu-id="1269c-122">カメラの画像に少なくとも6が含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1269c-122">Make sure that the camera image includes at least a 6 in.</span></span> <span data-ttu-id="1269c-123">(152 mm) 両側の境界線が横方向になっています。</span><span class="sxs-lookup"><span data-stu-id="1269c-123">(152 mm) border on both sides horizontally.</span></span> <span data-ttu-id="1269c-124">Microsoft Teams 室アプリのカメラプレビューを使用して、カメラの最終的な配置を決定することができます。</span><span class="sxs-lookup"><span data-stu-id="1269c-124">You can use the camera preview in the Microsoft Teams Rooms app to determine final placement of the camera.</span></span>

![コンテンツカメラの配置図](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a><span data-ttu-id="1269c-126">カメラの距離</span><span class="sxs-lookup"><span data-stu-id="1269c-126">Camera distances</span></span>

<span data-ttu-id="1269c-127">一般的なホワイトボードマーカーを使用すると、最適なリモートユーザーエクスペリエンスは、コンテンツカメラの画像の 1 ~ 2 mm の範囲でインクストロークを共有することになります。最良の結果を得るには、ピクセルあたり 1.5 mm を使用します。</span><span class="sxs-lookup"><span data-stu-id="1269c-127">Using typical whiteboard markers, the optimal remote user experience is to share ink strokes in the 1–2 mm per pixel range in the content camera image, and the best results use 1.5 mm per pixel.</span></span> <span data-ttu-id="1269c-128">サポートされているすべてのカメラには、1920 x 1080 の解像度が用意されており、その解像度を超えるものもあります。</span><span class="sxs-lookup"><span data-stu-id="1269c-128">All supported cameras provide 1920 x 1080 resolution, and some can exceed that resolution.</span></span>

<span data-ttu-id="1269c-129">ホワイトボードのカメラの距離は、カメラの解像度と HFoV と組み合わされ、ホワイトボードからの距離が決まります。</span><span class="sxs-lookup"><span data-stu-id="1269c-129">The distance of the camera from the whiteboard combines with the camera resolution and HFoV to determine the distance from the whiteboard.</span></span> <span data-ttu-id="1269c-130">次の表は、さまざまなホワイトボードサイズの距離の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="1269c-130">The following table shows examples of distances for various whiteboard sizes.</span></span> <span data-ttu-id="1269c-131">これらの値を出発点として使用して、コンテンツカメラの最終的な配置を決定することができます。</span><span class="sxs-lookup"><span data-stu-id="1269c-131">You can use these values as starting points to determine final placement of the content camera.</span></span>

<span data-ttu-id="1269c-132">**ホワイトボードとのカメラの距離**</span><span class="sxs-lookup"><span data-stu-id="1269c-132">**Camera distance from whiteboard**</span></span>

| <span data-ttu-id="1269c-133">カメラの視界</span><span class="sxs-lookup"><span data-stu-id="1269c-133">Camera HFoV</span></span> |<span data-ttu-id="1269c-134">3フィート。 (0.91 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-134">3 ft. (0.91 m)</span></span>     | <span data-ttu-id="1269c-135">6フィート。 (1.8 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-135">6 ft. (1.8 m)</span></span>    | <span data-ttu-id="1269c-136">9フィート (2.74 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-136">9 ft. (2.74 m)</span></span>        |<span data-ttu-id="1269c-137">12フィート。 (3.65 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-137">12 ft.  (3.65 m)</span></span>         | <span data-ttu-id="1269c-138">ホワイトボードからの最大距離</span><span class="sxs-lookup"><span data-stu-id="1269c-138">Max distance from Whiteboard</span></span>  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| <span data-ttu-id="1269c-139">80度</span><span class="sxs-lookup"><span data-stu-id="1269c-139">80°</span></span>         | <span data-ttu-id="1269c-140">1.79 ft。 (0.54 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-140">1.79 ft. (0.54 m)</span></span> | <span data-ttu-id="1269c-141">3.58 ft。 (1.09 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-141">3.58 ft. (1.09 m)</span></span>  | <span data-ttu-id="1269c-142">5.36 ft。 (1.6 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-142">5.36 ft. (1.6 m)</span></span>    |<span data-ttu-id="1269c-143">7.15 ft。 (2.17 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-143">7.15 ft. (2.17 m)</span></span> |<span data-ttu-id="1269c-144">7.51 ft。 (2.28 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-144">7.51 ft. (2.28 m)</span></span> |
| <span data-ttu-id="1269c-145">90度</span><span class="sxs-lookup"><span data-stu-id="1269c-145">90°</span></span>         | <span data-ttu-id="1269c-146">1.5 ft。 (0.45 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-146">1.5 ft. (0.45 m)</span></span> | <span data-ttu-id="1269c-147">3.00 ft。 (0.91 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-147">3.00 ft. (0.91 m)</span></span>   | <span data-ttu-id="1269c-148">4.5 ft。 (1.37 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-148">4.5 ft. (1.37 m)</span></span>    |<span data-ttu-id="1269c-149">6.0 ft。 (1.82 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-149">6.0 ft. (1.82 m)</span></span>    |<span data-ttu-id="1269c-150">6.3 ft。 (1.92 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-150">6.3 ft. (1.92 m)</span></span> |
| <span data-ttu-id="1269c-151">100度</span><span class="sxs-lookup"><span data-stu-id="1269c-151">100°</span></span>        | <span data-ttu-id="1269c-152">1.26 ft。 (0.38 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-152">1.26 ft. (0.38 m)</span></span>| <span data-ttu-id="1269c-153">2.52 ft。 (0.77 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-153">2.52 ft. (0.77 m)</span></span>   | <span data-ttu-id="1269c-154">3.78 ft。 (1.15 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-154">3.78 ft. (1.15 m)</span></span>   |<span data-ttu-id="1269c-155">5.03 ft。 (1.53 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-155">5.03 ft. (1.53 m)</span></span>   |<span data-ttu-id="1269c-156">5.29 ft。 (1.61 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-156">5.29 ft. (1.61 m)</span></span> |
| <span data-ttu-id="1269c-157">110度</span><span class="sxs-lookup"><span data-stu-id="1269c-157">110°</span></span>        | <span data-ttu-id="1269c-158">1.05 ft。 (0.32 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-158">1.05 ft. (0.32 m)</span></span>| <span data-ttu-id="1269c-159">2.10 ft。 (0.64 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-159">2.10 ft. (0.64 m)</span></span>   | <span data-ttu-id="1269c-160">3.15 ft。 (0.96 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-160">3.15 ft. (0.96 m)</span></span>   |<span data-ttu-id="1269c-161">4.2 ft。 (1.28 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-161">4.2 ft. (1.28 m)</span></span>    |<span data-ttu-id="1269c-162">4.41 ft。 (1.31 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-162">4.41 ft. (1.31 m)</span></span> |
| <span data-ttu-id="1269c-163">120度</span><span class="sxs-lookup"><span data-stu-id="1269c-163">120°</span></span>        | <span data-ttu-id="1269c-164">0.87 ft。 (0.26 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-164">0.87 ft. (0.26 m)</span></span>| <span data-ttu-id="1269c-165">1.73 ft。 (0.52 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-165">1.73 ft. (0.52 m)</span></span>   | <span data-ttu-id="1269c-166">2.60 ft。 (0.79 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-166">2.60 ft. (0.79 m)</span></span>   |<span data-ttu-id="1269c-167">3.46 ft。 (1.05 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-167">3.46 ft. (1.05 m)</span></span>   |<span data-ttu-id="1269c-168">3.64 ft。 (1.10 m)</span><span class="sxs-lookup"><span data-stu-id="1269c-168">3.64 ft. (1.10 m)</span></span> |
|             |               |                  |                  |        |                    |                  |

<span data-ttu-id="1269c-169">コンテンツのカメラと、ホワイトボードが搭載されている壁との距離は、カメラのモデルの HFoV によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1269c-169">The distance between the content camera and the wall the whiteboard is mounted on depends on the HFoV for that model of camera, which varies.</span></span> <span data-ttu-id="1269c-170">より大きな (120 度の) カメラをインストールして、壁に近づけたり、カメラの幅を狭くして壁から遠ざけたりします。</span><span class="sxs-lookup"><span data-stu-id="1269c-170">Install cameras with a larger HFoV (120 degrees for example) closer to the wall, and cameras with a narrower HFoV farther away from the wall.</span></span> <span data-ttu-id="1269c-171">選択されているカメラのインストールを開始する前に、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1269c-171">Check the HFoV before you start to install the chosen camera.</span></span>

<span data-ttu-id="1269c-172">10フィートを超えるホワイトボードを使用している場合 (3.65 m) または四隅 (フル壁のホワイトボードなど) を使用している場合は、カメラを中央の任意の場所に配置することができます。</span><span class="sxs-lookup"><span data-stu-id="1269c-172">If you have whiteboards larger than 12 ft. (3.65 m) or with no corners (like full wall whiteboards), you can place the camera anywhere in the middle.</span></span> <span data-ttu-id="1269c-173">強調表示されているホワイトボードの角が見つからない場合は、拡張ソフトウェアによって中央の領域が選択されます。</span><span class="sxs-lookup"><span data-stu-id="1269c-173">The enhancement software selects an area in the middle if it fails to find whiteboard corners.</span></span>

> [!NOTE]
> <span data-ttu-id="1269c-174">濃い色のテープなどの項目を使って、定義済みのコンテンツカメラ領域をフル壁のホワイトボードに作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1269c-174">You can use dark-colored tape or other items to create a defined content camera area on a full-wall white board.</span></span>
>
> <span data-ttu-id="1269c-175">常時マウントされている場合でも、カメラを可動三脚にマウントすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1269c-175">You can choose to have the camera mounted on a moveable tripod instead of a permanent mount.</span></span> <span data-ttu-id="1269c-176">三脚をホワイトボードの中央に配置します。</span><span class="sxs-lookup"><span data-stu-id="1269c-176">Place the tripod centered on the whiteboard.</span></span> <span data-ttu-id="1269c-177">この設定は一時的に、または機器を抜き合わせすることがほとんどない場合に使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1269c-177">This setup may be temporary or used where there is little chance of knocking over the equipment.</span></span> <span data-ttu-id="1269c-178">一時的なマウントを使用している場合は、最初の共有の後でカメラを移動すると、コンテンツのエンハンスメントが影響を受けることに注意してください。移動するには、もう一度共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1269c-178">If you use a temporary mount, remember that content enhancement will be impacted if you move the camera after the initial share and you will need to re-share to correct for movement.</span></span>
>
> <span data-ttu-id="1269c-179">ホワイトボードは、白くはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1269c-179">A writing board that isn't white is not supported.</span></span>

## <a name="supported-cameras"></a><span data-ttu-id="1269c-180">サポートされているカメラ</span><span class="sxs-lookup"><span data-stu-id="1269c-180">Supported cameras</span></span>

<span data-ttu-id="1269c-181">カメラをコンテンツカメラとして使用できるかどうかを判断するには、「 [USB オーディオとビデオの周辺機器の認定ファームウェアのバージョン](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1269c-181">To determine whether you can use a camera as a content camera, refer to [Certified firmware versions for USB audio and video peripherals](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals).</span></span>

<span data-ttu-id="1269c-182">または、 [aka.ms/teamsdevices](https://aka.ms/teamsdevices)の Microsoft Teams デバイス marketplace でサポートされているコンテンツカメラキットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1269c-182">Or, refer to the Microsoft Teams devices marketplace for supported Content Camera Kits at [aka.ms/teamsdevices](https://aka.ms/teamsdevices).</span></span>

## <a name="camera-settings"></a><span data-ttu-id="1269c-183">カメラの設定</span><span class="sxs-lookup"><span data-stu-id="1269c-183">Camera settings</span></span>

<span data-ttu-id="1269c-184">カメラが会議室にインストールされたら、その会議室の Microsoft Teams ルームコンソールで設定します。</span><span class="sxs-lookup"><span data-stu-id="1269c-184">Once the camera is installed in the room, set it up on that room's Microsoft Teams Rooms console:</span></span>

1. <span data-ttu-id="1269c-185">[**設定** ![の設定](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)] アイコンを選択し、管理者としてログインして、[**デバイスの設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1269c-185">Select **Settings** ![Settings icon](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png),  log in as Admin, and select **Device Settings**.</span></span>
2. <span data-ttu-id="1269c-186">[**カメラの既定値**] セクションで、コンテンツのカメラを選択し、[**コンテンツの拡張機能**] オプションが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1269c-186">In the **Camera Defaults** section, select the content camera and make sure that the **Content enhancements** option is selected.</span></span>
3. <span data-ttu-id="1269c-187">省略カメラが天井から装着されているために、カメラが上下逆さまに装着されている場合は、[**コンテンツカメラの回転180度**] オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1269c-187">(Optional) If the camera was installed upside down because the camera was mounted from the ceiling, check the **Rotate content camera 180°** option.</span></span>
4. <span data-ttu-id="1269c-188">[**保存して終了**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1269c-188">Select **Save and exit**.</span></span>

![コンテンツのカメラのセットアップ](../media/content-camera.png)

<span data-ttu-id="1269c-190">[XML 構成ファイル](xml-config-file.md)を使って、これらの設定をリモートで調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="1269c-190">You can also adjust these settings remotely using an [XML configuration file](xml-config-file.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1269c-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="1269c-191">See also</span></span>

[<span data-ttu-id="1269c-192">XML 構成ファイルを使用して、Microsoft Teams ルームコンソールの設定をリモートで管理する</span><span class="sxs-lookup"><span data-stu-id="1269c-192">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)

[<span data-ttu-id="1269c-193">Microsoft Teams の会議室の要件</span><span class="sxs-lookup"><span data-stu-id="1269c-193">Microsoft Teams Rooms requirements</span></span>](requirements.md)

> [!NOTE]
> <span data-ttu-id="1269c-194">Microsoft Surface Pro ベースのコンソール (Logitech Smartdock や Crestron SR など) を搭載した一部の Microsoft Teams Room デバイスは、まだコンテンツのカメラをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1269c-194">Certain Microsoft Teams Room devices that have Microsoft Surface Pro based consoles (such as, Logitech Smartdock and Crestron SR) do not yet support content camera.</span></span> <span data-ttu-id="1269c-195">これらのデバイスのサポートは、後で CY2019 に追加されます。</span><span class="sxs-lookup"><span data-stu-id="1269c-195">Support for these devices will added later in CY2019.</span></span> 
>
