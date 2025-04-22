# Use the official Python image as the base image
FROM python:3.9

#install pip
RUN apt-get update && apt-get install -y python3-pip

# Set the working directory in the container
WORKDIR /envia_pedidos

# Copy the requirements file to the working directory
COPY . /envia_pedidos

# Install the Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Run the application
CMD ["python", "envia_pedido.py"]