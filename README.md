# Python-QRCode
Python二维码生成程序
import qrcode：导入了 qrcode 模块，该模块提供了生成 QR 码的功能。

from PIL import Image：从 PIL 库中导入 Image 模块，用于处理和操作图像。

def generate_qrcode(text, filename):：定义了一个名为 generate_qrcode 的函数，它接受两个参数：text（要编码成 QR 码的内容）和 filename（保存生成的 QR 码图像的文件名）。

qr = qrcode.QRCode(version=1, error_correction=qrcode.constants.ERROR_CORRECT_H, box_size=10, border=4)：创建了一个 qrcode 模块中的 QRCode 类的实例。version 参数指定了 QR 码的大小（这里使用版本 1），error_correction 设置了高级的错误纠正级别，box_size 决定了每个 QR 码方块的像素大小，border 定义了 QR 码周围的边框大小。

qr.add_data(text)：将提供的 text 添加到 QR 码的数据中。

qr.make(fit=True)：基于提供的数据生成 QR 码矩阵。fit 参数设置为 True，允许 QR 码根据数据自动调整大小。

img = qr.make_image(fill_color="black", back_color="white")：创建一个代表 QR 码图像的 PIL 的 Image 对象。fill_color 参数设置 QR 码模块的颜色（这里是黑色），back_color 参数设置背景颜色（这里是白色）。

img.save(filename)：将 QR 码图像保存到指定的 filename。

img.show()：使用系统默认的图像查看器显示 QR 码图像。

generate_qrcode("黃文定", "qrcode.png")：调用 generate_qrcode 函数，传入文本 "黃文定"（将被编码到 QR 码中）和文件名 "qrcode.png"（生成的 QR 码图像将保存在该文件中）。
