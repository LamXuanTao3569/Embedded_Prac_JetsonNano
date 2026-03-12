# Công cụ biên dịch
CC = aarch64-linux-gnu-gcc

# Biến môi trường TARGET_ROOTFS phải được định nghĩa trước
# CFLAGS: Đường dẫn tiêu đề
CFLAGS = --sysroot=$(TARGET_ROOTFS) \
         -I$(TARGET_ROOTFS)/usr/include/gstreamer-1.0 \
         -I$(TARGET_ROOTFS)/usr/include/glib-2.0 \
         -I$(TARGET_ROOTFS)/usr/lib/aarch64-linux-gnu/glib-2.0/include

# LDFLAGS: Đường dẫn thư viện
LDFLAGS = --sysroot=$(TARGET_ROOTFS) \
          -L$(TARGET_ROOTFS)/usr/lib/aarch64-linux-gnu

# LIBS: Thư viện liên kết
LIBS = -lgstreamer-1.0 -lgobject-2.0 -lglib-2.0

# Mục tiêu mặc định
all: gst_h265_encode

# Quy tắc biên dịch
gst_h265_encode: gst_h265_encode.c
	$(CC) $(CFLAGS) gst_h265_encode.c -o gst_h265_encode $(LDFLAGS) $(LIBS)

# Quy tắc dọn dẹp
clean:
	rm -f gst_h265_encode
